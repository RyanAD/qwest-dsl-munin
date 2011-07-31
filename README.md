This is a very early version of two munin plugins for Qwest DSL modems. This currently graphs:

* Power Down
* Power Up
* Attenuation Down
* Attenuation Up
* SNR Down
* SNR Up
* Connection speed (up / down)

Installing:

* [Download](http://github.com/icedrake/qwest-dsl-munin/tarball/master) and extract
* Run: `chmod a+x dsl-*`
* Copy or symlink both plugins into /etc/munin/plugins
* Edit /etc/munin/plugin-conf.d/munin-node and add the following:

```
[dsl-connspeed]
env.DSLMODEMIP 192.168.0.1
env.DSLUSER admin
env.DSLPASS admin

[dsl-stats]
env.DSLMODEMIP 192.168.0.1
env.DSLUSER admin
env.DSLPASS admin
```
DSLUSER and DSLPASS are optional.

* Now restart munin-node `service munin-node restart`

You can test the setup by running  `munin-run dsl-connspeed` and `munin-run dsl-stats`
I have only tested this with my Q1000 modem, let me know if it works for yours! I think it should work if your modem WAN status page looks similar to this:

![Qwest WAN Status Page](http://www.mandrake.us/qwest-wan-status2.jpg)


