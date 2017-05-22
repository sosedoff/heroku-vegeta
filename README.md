# heroku-vegeta

Run [vegeta](https://github.com/tsenart/vegeta) as a distributed load testing tool
on Heroku for free. This project has two goals: explore diffent ways to deploy
applications on heroku platform and provide a simple tool to easily run various
load testing scenarios. 

![Example Plot](/plot.png)

## Usage

Clone repository:

```
git clone https://github.com/sosedoff/heroku-vegeta.git
cd heroku-vegeta
```

Make sure your heroku cli is working:

```
heroku apps
```

Copy example configuration file:

```
cp config.json.example config.json
```

After you make changes to config file, run setup command:

```
./script/setup
```

Once done, you can start the test:

```
./script/run
```

Make sure to remove all test apps after you're done:

```
./script/teardown
```

## Config

Example configuration for testing:

```
{
  "nodes": 3,
  "targets": "GET https://mywebsite.com",
  "duration": "30s",
  "rate": "50"
}
```

Options:

- `nodes` - Number of heroku applications to spawn
- `targets` - List of URLS to hit
- `duration` - Test duration. `10s, 30s, 1m, 5m`, etc
- `rate` - Number of requests per second per node

## License

The MIT License (MIT)

Copyright (c) 2017 Dan Sosedoff <dan.sosedoff@gmail.com>