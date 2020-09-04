# PinningWebView

In master we're setting a bad pinning intentionally. So it should not load the popular Colombian news website https://www.eltiempo.com. 

In working branch, we set the right pin, there are several ways to get the SHA so you don't have to use the eltiempo.com website and get your very own page, I like to use: 'openssl s_client -showcerts -servername eltiempo.com -connect eltiempo.com:443 </dev/null | openssl x509 -outform DER > eltiempo.der'

After that, execute "python cert_generator.py --type DER eltiempo.der" the python script is from our Trustkit friends, check their powerful tools when you can. 

Now you have the public key hash. 


The expected behavior is it doesn't load the website on master but in working branch. 

Feel free to get in touch at amaca@veritran.com

