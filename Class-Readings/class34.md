
# Django Settings: Best practices

- Keep settings in environment variables.
- Write default values for production configuration (excluding secret keys and tokens).
- Don’t hardcode sensitive settings, and don’t put them in VCS.
- Split settings into groups: Django, third-party, project.
- Follow naming conventions for custom (project) settings.

# SSH

SSH, or Secure Shell, is a remote administration protocol that allows users to control and modify their remote servers over the Internet.

- It provides a mechanism for authenticating a remote user, transferring inputs from the client to the host, and relaying the output back to the client.

The SSH command consists of 3 distinct parts:

    ssh {user}@{host}

- **ssh** - instructs your system that you want to open an encrypted Secure Shell Connection
- **user** - the account you want to access
- **host** - refers to the computer you want to access.This can be an IP Address or a domain name

There are three different encryption technologies used by SSH:

- Symmetrical encryption: Symmetric encryption is a form of encryption where a secret key is used for both encryption and decryption of a message by both the client and the host. Effectively, any one possessing the key can decrypt the message being transferred. Symmetrical encryption is often called shared key or shared secret encryption. There is usually only one key that is used, or sometimes a pair keys where one key can easily be calculated using the other key.

- Asymmetrical encryption: asymmetrical encryption uses two separate keys for encryption and decryption. These two keys are known as the public key and the private key. Together, both these keys form a public-private key pair.

- Hashing: One-way-hash functions differ from the above two forms of encryption in the sense that they are never meant to be decrypted. They generate a unique value of a fixed length for each input that shows no clear trend which can exploited. This makes them practically impossible to reverse. SSH uses hashes to verify the authenticity of messages. This is done using HMACs, or Hash-based Message Authentication Codes. This ensures that the command received is not tampered with in any way.

## How Does SSH Work with These Encryption Techniques

The way SSH works is by making use of a client-server model to allow for authentication of two remote systems and encryption of the data that passes between them.

SSH operates on TCP port 22 by default (though this can be changed if needed). The host (server) listens on port 22 (or any other SSH assigned port) for incoming connections. It organizes the secure connection by authenticating the client and opening the correct shell environment if the verification is successful.

Here is how the algorithm works at a very basic level:

1. Both the client and the server agree on a very large prime number, which of course does not have any factor in common. This prime number value is also known as the seed value.
2. Next, the two parties agree on a common encryption mechanism to generate another set of values by manipulating the seed values in a specific algorithmic manner. These mechanisms, also known as encryption generators, perform large operations on the seed. An example of such a generator is AES (Advanced Encryption Standard).
3. Both the parties independently generate another prime number. This is used as a secret private key for the interaction.
4. This newly generated private key, with the shared number and encryption algorithm (e.g. AES), is used to compute a public key which is distributed to the other computer.
5. The parties then use their personal private key, the other machine’s shared public key and the original prime number to create a final shared key. This key is independently computed by both computers but will create the same encryption key on both sides.
6. Now that both sides have a shared key, they can symmetrically encrypt the entire SSH session. The same key can be used to encrypt and decrypt messages (read: section on symmetrical encryption).

# Whitenoise

WhiteNoise takes care of best-practices for you, for instance:

- Serving compressed content (gzip and Brotli formats, handling Accept-Encoding and Vary headers correctly)

- Setting far-future cache headers on content which won’t change

**Install with:**

    pip install whitenoise
    or
    poetry add whitenoise

**settings.py**

-add WhiteNoise to the MIDDLEWARE list, above all other middleware apart from Django’s SecurityMiddleware:


    MIDDLEWARE = [
    #'django.middleware.security.SecurityMiddleware',
    'whitenoise.middleware.WhiteNoiseMiddleware',
     #...
    ]


Want forever-cacheable files and compression support? Just add this to your settings.py:

    STATICFILES_STORAGE = 'whitenoise.storage.CompressedManifestStaticFilesStorage'

# CORS

Cross-origin resource sharing (CORS) is a mechanism that allows restricted resources on a web page to be requested from another domain outside the domain from which the first resource was served.


The CORS standard describes new HTTP headers which provide browsers with a way to request remote URLs only when they have permission. Although some validation and authorization can be performed by the server, it is generally the browser's responsibility to support these headers and honor the restrictions they impose.


For Ajax and HTTP request methods that can modify data (usually HTTP methods other than GET, or for POST usage with certain MIME types), the specification mandates that browsers "preflight" the request, soliciting supported methods from the server with an HTTP OPTIONS request method, and then, upon "approval" from the server, sending the actual request with the actual HTTP request method. Servers can also notify clients whether "credentials" (including Cookies and HTTP Authentication data) should be sent with requests.


Suppose a user visits http://www.example.com and the page attempts a cross-origin request to fetch the user's data from http://service.example.com. A CORS-compatible browser will attempt to make a cross-origin request to service.example.com as follows.

1. The browser sends the GET request with an extra Origin HTTP header to service.example.com containing the domain that served the parent page:

    Origin: http://www.example.com

2. The server at service.example.com may respond with:

- The requested data along with an Access-Control-Allow-Origin (ACAO) header in its response indicating the requests from the origin are allowed. For example in this case it should be:

    Access-Control-Allow-Origin: http://www.example.com

- The requested data along with an Access-Control-Allow-Origin (ACAO) header with a wildcard indicating that the requests from all domains are allowed:

    Access-Control-Allow-Origin: *

- An error page if the server does not allow a cross-origin request


# References

[Django Settings Best Practices](https://djangostars.com/blog/configuring-django-settings-best-practices/)

[SSH Tutorial](https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work)

[White Noise](http://whitenoise.evans.io/en/stable/)

[IaaS](https://en.wikipedia.org/wiki/Infrastructure_as_a_service)

[PaaS](https://en.wikipedia.org/wiki/Platform_as_a_service)

[CORS](https://en.m.wikipedia.org/wiki/Cross-origin_resource_sharing)