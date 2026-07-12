## Note
I took the notes below from the book ``The Web Application
Hacker’s Handbook``.This book was published in 2007.

# chapter 1

## The Evolution of Web Applications

- In the early days of the Internet, the World Wide Web consisted only of web sites.
- These were essentially information repositories containing static documents,
and web browsers were invented as a means of retrieving and displaying those
documents(web sites are made for the purpose of displying static content.)
- Any security threats arising from hosting a web site related
largely to `vulnerabilities in web server software` (of which there were many).
- an attacker would typically modify the files
on the server to `deface the web site’s contents`, or `use the server’s storage and
bandwidth to distribute “warez.”`
- Today, the World Wide Web is almost unrecognizable from its earlier form.
The majority of sites on the web are in fact applications.They
are highly functional, and rely upon `two-way flow of information` between the
server and browser. They support registration and login, financial transactions,
search, and the authoring of content by users.
- Web applications bring with them new and significant security threats.
- web applications normally require connectivity to internal computer systems that contain highly sensitive data and are able to perform powerful business functions.

## Web Application Security

- some common categories of vulnerability in web applications:-
      
    - Broken authentication
    
    - Broken access controls
    
    - SQL injection
    
    - Cross-site scripting
    
    - Information leakage
## The Core Security Problem: Users Can Submit Arbitrary Input
- Because the client is outside of the application’s control, users can `submit completely arbitrary
input` to the server-side application.
- The application must assume that all input
is potentially malicious, and must take steps to ensure that attackers cannot use
crafted input to compromise the application by interfering with its logic and
behavior and gaining unauthorized access to its data and functionality.
- The majority of attacks against web applications involve `sending input to
the server which is crafted to cause some event that was not expected or
desired by the application’s designer`.
## The New Security Perimeter
- Before the rise of web applications, organizations’ efforts to secure themselves
against external attack were largely focused on the network perimeter.
- Defending this perimeter entailed `hardening and patching the services that it needed
to expose, and firewalling access to others`.(before web applications,organizations would just patch server side applications,slap it with firewall then they'll call it a day to secure web sites.)
- but this won't work with web applications.
- For an application to be accessible by its users, the perimeter `firewall must allow inbound connections to the server over HTTP/S`.
- And for the application to function, the `server must be allowed to connect to supporting back-end systems`, such as databases, main-frames, and financial and logistical systems.
- These systems often lie at the core of the organization’s operations and reside behind several layers of network level defenses.
- If a vulnerability exists within a web application, then an attacker on the public Internet may be able to compromise the organization’s core back-end systems solely by submitting crafted data from his web browser. This data will sail past all of the organization’s network defenses.
- A single line of defective code in a single web application can render an organization’s internal systems vulnerable.
- defenses against attacks must be implemented within the applications themselves.
- For example, suppose that an attacker wishes to “hack in” to a bank’s systems
and steal money from users’ accounts. Before the bank deployed a web
application, the attacker might have needed to find a vulnerability in a publicly
reachable service, exploit this to gain a toehold on the bank’s DMZ, penetrate
the firewall restricting access to its internal systems, map the network to find
the mainframe computer, decipher the arcane protocol used to access it, and
then guess some credentials in order to log in. However, if the bank deploys a
vulnerable web application, then the attacker may be able to achieve the same
outcome simply by modifying an account number in a hidden field of an HTML
form.
# chapter 2