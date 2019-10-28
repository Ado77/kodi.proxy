# kodi.proxy

```
git clone https://github.com/matthuisman/kodi.proxy
cd kodi.proxy
pip install virtualenv
virtualenv --python=python2.7 .env
source .env/bin/activate
pip install -r requirements.txt
chmod +x proxy.py
chmod +x tvh.sh
./proxy.py
```

Example TvHeadend URL:
```
pipe:///root/kodi.proxy/tvh.sh "plugin://plugin.video.kayo.sports/?_=play&id=53217&_l=.pvr"
```


For anyone brave enough to try get Kayo working through TvHeadend,
my Kodi proxy script should now work.

https://github.com/matthuisman/kodi.proxy

Here are some basic instructions

apt-get install wget python-virtualenv
cd ~
wget -O – https://github.com/matthuisman/kodi.proxy/tarball/master | tar xz
mv matthuisman-kodi.proxy* kodi.proxy
cd kodi.proxy
virtualenv --no-site-packages --python=python2.7 .env
source .env/bin/activate
pip install -r requirements.txt

Then you can just run

./proxy.py "install://plugin.video.kayo.sports"

Then run

./proxy.py "plugin://plugin.video.kayo.sports/?_=login"

Once it logs in, just type -1 to exit (or CTRL-C)

It's now all setup and ready to go.

In TvHeadend, add an IPTV Network (not Automatic).
Name it Kayo and enable it.

Go to Muxes, Add Mux, Select Kayo network.

Set the url to:
pipe:///root/kodi.proxy/tvh.sh "plugin://plugin.video.kayo.sports/?_=play&id=53217&_l=.pvr"

Replace /root/kodi.proxy/ with the path to your kodi.proxy directory.

Set the name to:
Fox Sports News

the tvh.sh will run the proxy.py script, get the url and headers and then call ffmpeg

Make sure ffmpeg is installed and available in $PATH

Add more channels as you need,
Just copy the urls, names, logos from http://i.mjh.nz/au/Kayo/kodi.m3u8
