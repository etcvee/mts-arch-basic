[parallels@fedora module_08]$ curl http://localhost:8081/authors/1
[{&quot;id&quot;:1,&quot;first_name&quot;:&quot;Liam&quot;,&quot;last_name&quot;:&quot;Moore&quot;,&quot;email&quot;:&quot;Liam_Moore4478@iaart.store&quot;,&quot;title&quot;:&quot;Call Center Representative&quot;,&quot;birth_date&quot;:&quot;1981-11-27 13:44:56Z&quot;}]

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;title&quot;:&quot;First Presentation&quot;,&quot;last_name&quot;:&quot;Moore&quot;}

[parallels@fedora module_08]$ sudo docker-compose stop service_author
Stopping service_author ... <font color="#26A269">done</font>

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;detail&quot;:&quot;&gt;&gt;&gt; Error Connecting&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;detail&quot;:&quot;&gt;&gt;&gt; Error Connecting&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;detail&quot;:&quot;&gt;&gt;&gt; Error Connecting&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;detail&quot;:&quot;&gt;&gt;&gt; Error Connecting&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;detail&quot;:&quot;&gt;&gt;&gt; Error Connecting&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;title&quot;:&quot;First Presentation&quot;,&quot;last_name&quot;:&quot;temporary unavailable&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;title&quot;:&quot;First Presentation&quot;,&quot;last_name&quot;:&quot;temporary unavailable&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;title&quot;:&quot;First Presentation&quot;,&quot;last_name&quot;:&quot;temporary unavailable&quot;}

[parallels@fedora module_08]$ sudo docker-compose start service_author
Starting service_author ... <font color="#26A269">done</font>

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;title&quot;:&quot;First Presentation&quot;,&quot;last_name&quot;:&quot;Moore&quot;}

[parallels@fedora module_08]$ sudo docker-compose stop service_author
Stopping service_author ... <font color="#26A269">done</font>

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;detail&quot;:&quot;&gt;&gt;&gt; Error Connecting&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;detail&quot;:&quot;&gt;&gt;&gt; Error Connecting&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;detail&quot;:&quot;&gt;&gt;&gt; Error Connecting&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;detail&quot;:&quot;&gt;&gt;&gt; Error Connecting&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;detail&quot;:&quot;&gt;&gt;&gt; Error Connecting&quot;}

[parallels@fedora module_08]$ sudo docker-compose start service_authortionsAndAuthor
Starting service_author ... <font color="#26A269">done</font>

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;title&quot;:&quot;First Presentation&quot;,&quot;last_name&quot;:&quot;temporary unavailable&quot;}

[parallels@fedora module_08]$ curl http://localhost:8083/presentationsAndAuthor/First%20Presentation
{&quot;title&quot;:&quot;First Presentation&quot;,&quot;last_name&quot;:&quot;Moore&quot;}
</pre>