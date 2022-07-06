<h1><b> Compile OpenSSL Static and Shared</b></h1>


Download Compiler Helfer:

```
https://www.perl.org/get.html
```

```
https://www.nasm.us/pub/nasm/releasebuilds/2.15.05/win64/
```

<br><br>

Download das aktuelle Openssl vom github

```
https://github.com/openssl/openssl/
```

entpacken in ein Verzeichniss openssl-master

jetzt die Nativ Tools command Prompt öffnen x86 oder x64  von Visual Studio 

<code>perl --version</code> 

<code>nasm --version</code>

<code>nmake</code>


testen ob perl da ist 

jetzt legen wir ein Build verzeichniss an

<code>mkdir build </code>

<code>mkdir build/x32 </code>

<code>mkdir build/x32/ssl </code>

<code>mkdir build/x32/lib </code>

<code>mkdir build/x32/dll </code>


Eingabe in die Command Zeile
```
cpan -i Text::Template
```
```
cpan -i Test::More
```


<h3>Configuration Shared and Static Lib </h3>


<h4>Shared Config - DEBUG</h4>

```
perl Configure VC-WIN32 --debug --prefix=C:\openssl-master\build\x32\lib --openssldir=c:\openssl-master\build\x32\ssl
```

```
perl Configure VC-WIN64A --debug --prefix=C:\openssl-master\build\x64\lib --openssldir=c:\openssl-master\build\x64\ssl
```

<h4>Shared Config - RELEASED</h4>

```
perl Configure VC-WIN32 --prefix=C:\openssl-master\build\x32\lib --openssldir=c:\openssl-master\build\x32\ssl
```

```
perl Configure VC-WIN64A --prefix=C:\openssl-master\build\x64\lib --openssldir=c:\openssl-master\build\x64\ssl
```

<h4>Static Config - DEBUG</h4>

```
perl Configure VC-WIN32 --debug --prefix=C:\openssl-master\build\x32\lib --openssldir=c:\openssl-master\build\x32\ssl no-shared
```

```
perl Configure VC-WIN64A --debug --prefix=C:\openssl-master\build\x64\lib --openssldir=c:\openssl-master\build\x64\ssl no-shared
```

<h4>Static Config - RELEASED</h4>

```
perl Configure VC-WIN32 --prefix=C:\openssl-master\build\x32\lib --openssldir=c:\openssl-master\build\x32\ssl no-shared
```

```
perl Configure VC-WIN64A --prefix=C:\openssl-master\build\x64\lib --openssldir=c:\openssl-master\build\x64\ssl no-shared
```



<h4>Compile </h4>

```
nmake
```

<h4>Cleaning and Test Install</h4>

```
nmake clean
```

```
nmake test
```

```
nmake install_sw
```



