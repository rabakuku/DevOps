# 2_Monitoring-Jenkins

##### For More: [Monitoring Jenkins](https://www.jenkins.io/doc/book/system-administration/monitoring/)

Username: admin

Password: Adm!n321

### Prometheus

#### Install Prometheus metrics

##### More on Prometheus: [Prometheus metrics | Jenkins plugin](https://plugins.jenkins.io/prometheus/)

#### Install Prometheus plugin

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/kAQ8TecWS2I2sBkF-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/kAQ8TecWS2I2sBkF-image.png)

#### Need to Restart

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/8A8ESLFfqBN67K6F-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/8A8ESLFfqBN67K6F-image.png)

```
system jenkins restart
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/LwLWPR9OWiZwjHfw-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/LwLWPR9OWiZwjHfw-image.png)

#### Which endpoint is the prometheus plugin exposed on by default?

- /Prometheus
- navegate to [https://localhost:8085/Prometheus](https://localhost:8085/Prometheus)
    - you can see all the metrics pulled by prometheus

#### Prometheus config for Jenkins

Prometheus config for Jenkins is missing.. Let's add it!

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/69XPA5GZDM34pdCd-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/69XPA5GZDM34pdCd-image.png)

##### Update the prometheus

Update the prometheus configuration file located at

```
/etc/prometheus/prometheus.yml 
```

with the following

```
- job_name: 'Jenkins'
  metrics_path: /prometheus/
  static_configs:
    - targets: ['localhost:8085']
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/EIQXCYVc5CfC5v3T-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/EIQXCYVc5CfC5v3T-image.png)

#####  Restart prometheus using the below command

```
service prometheus restart
```

##### Jenkins is now being Monitored

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/aPfxh1JNokpm493f-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/aPfxh1JNokpm493f-image.png)

#### Queries in Prometheus

Now lets test out some queries in Prometheus. and execute the following query:

```
jenkins_job_count_value
```

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/Ws4hu409gUjJ4i4l-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/Ws4hu409gUjJ4i4l-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/FAIWyRkCdEmZfvDk-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/FAIWyRkCdEmZfvDk-image.png)

### Graphana

First of all, let us add Prometheus datasource in Grafana. Follow below given steps for that:

##### -&gt; Login into Grafana and click on Add your first datasource.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/cz1avJzE9rulGauz-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/cz1avJzE9rulGauz-image.png)

##### -&gt; Then select Prometheus and enter http://localhost:9090 in the URL box.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/nFZWaJWzY3eEeg2a-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/nFZWaJWzY3eEeg2a-image.png)

##### -&gt; Finally click on Save and test button at the bottom.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/mNU5qyAvXu6kOVLS-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/mNU5qyAvXu6kOVLS-image.png)

##### -&gt; Click on Grafana logo to move back to the dashboard.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/q3BSxn1NwJS0n3JG-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/q3BSxn1NwJS0n3JG-image.png)

##### Create your first dashboard.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/JSccE8wHbG1Odba1-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/JSccE8wHbG1Odba1-image.png)

-&gt; Then click on Add visualization and at the bottom enter jenkins\_job\_count\_value in the Metrics browser box.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/pDL5OQ13VUy99eqR-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/pDL5OQ13VUy99eqR-image.png)

-&gt; Make sure Prometheus is selected as the Data source.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/XP1SUJrXLR27xXqs-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/XP1SUJrXLR27xXqs-image.png)

-&gt; On the right side under Panel options, enter Jenkins Jobs Count in Title.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/XP1SUJrXLR27xXqs-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/XP1SUJrXLR27xXqs-image.png)

-&gt; Click on Apply button on the top right corner.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/XP1SUJrXLR27xXqs-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/XP1SUJrXLR27xXqs-image.png)

-&gt; Finally click on the Save dashboard button (second button on the top right).

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/wdpE8W8Isumi0RAP-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/wdpE8W8Isumi0RAP-image.png)

-&gt; Enter dashboard name as Jenkins and save it.

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/YzeHaOvUSPpteCWL-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/YzeHaOvUSPpteCWL-image.png)

[![image.png](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/scaled-1680-/zjNbE9wRhapOPQIp-image.png)](https://bookstack.besthomelabevar.xyz/uploads/images/gallery/2024-06/zjNbE9wRhapOPQIp-image.png)