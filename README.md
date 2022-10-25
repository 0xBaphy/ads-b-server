# ADS-B server

Track planes, helicopters and more using easy to get hardware, and submits data to [ADSBexchange](https://www.adsbexchange.com/)

Things you'll need

- A machine running Linux or MacOs
- [RTL-SDR Dongle](https://www.rtl-sdr.com/) (You can also get knockoffs from aliexpress, which work just fine for this application)
- [A 1090MHz antenna]("1090MHz antenna" buy) (Or, you can [build your own!](https://lucsmall.com/2017/02/06/making-antennas-for-1090mhz-ads-b-aircraft-tracking/))

## Steps

1. Clone this repository

```sh
git clone https://github.com/0xBaphy/ads-b-server
cd ads-b-server
```

2. `.env` file

Fill the required field on `env.example`.

- To get your latitude, longitude and altitude you can use [this site](https://www.freemaptools.com/elevation-finder.htm)
- To get a valid UUID, you can use [this site](https://www.uuidgenerator.net/) or you can run `cat /proc/sys/kernel/random/uuid` on a terminal

Then run `cp env.example .env`

3. Run it

```sh
sudo docker-compose up
```

If everything goes well, you can now go to `http://localhost:8080` and see a map with all the things you've detected.
And, if you go to `https://www.adsbexchange.com/myip/` you should see to smiling faces, indicating you're correctly feeding data to ADS-B Exchange
