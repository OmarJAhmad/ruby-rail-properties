# ruby-rail-properties CVE-2023-23138

This is a short view of ruby on rails properties misconfiguration 
sometimes developers forgot to disable this endpoint `/rails/info/properties`


if this endpoint was enabled on the host, that's mean an attacker can see part/all of the following information:

- Application root
- Environment mode
- Database adapter
- Database schema version
- Ruby version
- RubyGems version
- Rack version
- Rails version
- JavaScript Runtime
- Active Record version
- Action Pack version
- Action Mailer version
- Active Support version
- list of Middlewares


# Testing on mass scale

I've create a nuclei template to check this missconfiguration you can use it as following:

`nuclei -l <path of domains> -t ruby-rail-properties.yaml -rl 3000 -bs 3000`

![image](https://user-images.githubusercontent.com/42843641/210562192-c532f5de-f099-46de-b072-f98a2efe7eba.png)

the results was also manually verfied to avoid false positives 

a sample of one host would be similar to this :

![image](https://user-images.githubusercontent.com/42843641/210563831-498e73e5-0dc1-4c66-8d38-bd5c23c66252.png)
