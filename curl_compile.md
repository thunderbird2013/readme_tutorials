
<h1> CURL - MASTER SHARED AND STATIC COMPILE</h1>

Download the from Url [CURL-MASTER](https://github.com/curl/curl)

```
git clone https://github.com/curl/curl.git
```

<h4>Tools required</h4>
* cUrl Source Download Last Version [CURL-MASTER](https://github.com/curl/curl)<br>
* Microsoft Visual C++ 2019 or 2022 Community or Pro Download [here]()<br>
* Win32 OpenSSL:<br> 
* Install Win32 OpenSSL; by default it Install to C:\OpenSSL-Win32<br>
* Install Visual Studio 2019 or 2022<br> 
<br>
Entpacken Sie alle Datein und starten den X86 oder X64 Native Tools Command Prompt from Visual Studio

<h3>Building cUrl</h3>
<hr>

```
set RTLIBCFG=static
```

* change in cUrl Winbuild Directory<br>
* VC=X (2019(16) = X) (2022(17) =X)

<b> Compile static with OpenSSL </b>


```
nmake /f Makefile.vc mode=static WITH_SSL=static WITH_DEVEL=C:\OpenSSL-Win32 VC=X ENABLE_SSPI=no ENABLE_IDN=no ENABLE_WINSSL=no DEBUG=no MACHINE=x86 GEN_PDB=no ENABLE_IPV6=yes
```


<b>Compile static without OpenSSL</b>
```
nmake /f Makefile.vc mode=static vc=X debug=yes
```


* Additionally, #define CURL_STATICLIB in your application before linking.

