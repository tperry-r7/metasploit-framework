% Workspaces

From the user perspective, you often start with a set of hosts. In penetration testing, you find these hosts through information gathering. In development, you probably have your own set of virtual machines to test modules or specific features. If you need a way to manage these hosts, then you need a workspace.

The Metasploit workspace allows you to import, manage, and then export so that you can reuse the data with your favorite tools. Framework also uses the same workspace to automatically report what it knows about the host it’s currently engaging: from vulnerability information, random notes, and stolen information.

## Importing scan results
 
1. In your terminal (or command prompt), start msfconsole:
   `$ ./msfconsole`
2. If you don’t actually have a database connected, then do:
    `db_connect user:pass@localhost/msf`
3. By default, you are connected to a default workspace. Start with a new one:
    `workspace -a msf_lab`
4. Now, import mslab_nmap.xml
   ` db_import mslab_nmap.xml`

After the results are imported, you have these commands to manage the database. Each command also has a set of options that you can see with -h:

| Name | Description |
|--|--|
| cred | List all credentials in the database |
| hosts| List all hosts in the database |
| loot | List all loot in the database |
| notes | List all notes in the database |
| services | List all services in the database |
| vulns | List all vulnerabilities in the database |\



## Prioritize targets

Now that you have all the information stored in the database, you need to figure out what’s essential for you. For example, if you’re only testing web applications, obviously all you want is HTTP or HTTPS services, and you can tell msfconsole only to show you HTTP and HTTPS services. You can even sort, dump the results to an external file, so you can load that as an IP list and share it with other third-party tools you like. Being able to prioritize targets quickly is important for better work efficiency, especially for a large network.

Some handy examples:


1. List a specific range of hosts that are up:

`msf > hosts -u -R 10.20.36.51-10.20.36.68`

2. List all the hosts with HTTP, HTTPS, and WinRM:

`msf > services -r tcp -p 80,8181,5985`

3. List all the Windows hosts:
    1. Ideally, the hosts command should allow you to do this:
   
        `msf > hosts -S "Microsoft Windows"`

    2. If not, then you’ll need to rely on the services command:

    	`msf > services -S "Microsoft"`

4. List all the hosts vulnerable to a specific bug (mslab_nmap.xml doesn’t have any data for this, maybe try a Nexpose one):

	`msf > vulns -S "ms09-001"`

5. Tag a range of hosts:

	`msf > hosts -R 192.168.1.1/24 -t Sales`

6. Search for hosts by a specific tag:

	`msf > hosts -S Sales -c “address,name,tags”`

7. Export isn’t always available in every command, but with the spool command you can get creative with this:
    1. `spool /tmp/vuln_hosts.txt` 
    2. `vulns -S "ms09-001"`
    3. `spool off`
    4. Enter irb, and do this to collect the hosts:
  
```bash
buf = File.open('/tmp/nexpose_test.txt', 'rb') {|f| f.read}
buf = buf.scan(/host=([\d+\.]+)/).flatten.uniq * "\n"
File.open('/tmp/new_nexpose_list.txt', 'wb') {|f| f.write(buf)}
```