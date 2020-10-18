# Mara X Monitoring

![Granfana Preview](./preview.png "Granfana Preview")

Take serial connection from Mara X containing temperature data a persist in a database and expose via grafana.

Docker will persist DB storage using volumes so restarts won't cause data loss.

Tested on a Raspberry Pi. Requires companion [marax-telegraf-agent](https://github.com/laebshade/marax-telegraf-agent) docker container running on Raspberry Pi Zero W or better.

All credit to the author of this [post](https://www.reddit.com/r/espresso/comments/hft5zv/data_visualisation_lelit_marax_mod/) for doing so much of the ground work!

## How to run

Run grafana / influxDB / ingestion via docker-compose with the following

```shell
[sudo] docker-compose up --build
```

This can now be backgrounded.

## What do I need?

- Lelit Mara X PL62 espresso machine ([link](https://marax.lelit.com/index-eng.html))
- Serial to USB cable ([link](https://www.amazon.co.uk/gp/product/B01N4X3BJB/ref=ppx_yo_dt_b_asin_title_o06_s00?ie=UTF8&psc=1))
- Computer capable of running linux & Docker, like a Raspberry Pi ([link](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/))

## Other

- Influx DB retention policy set to 2 weeks, see [here](./config/influxdb/influxdb-init.iql)
