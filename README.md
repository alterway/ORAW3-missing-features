# ORAW3 missing features

This repository provides a pipeline system using [ORAW2 issue-weight](https://git.rnd.alterway.fr/overboard/openreq/oraw2_issue-weight) algorithms to improves the precision of the system. This pipeline allows the intervention of humans operators to qualify ambiguous cases.

This service was created as a result of the OpenReq project funded by the European Union Horizon 2020 Research and Innovation programme under grant agreement No 732463.

## Pipeline structure

The explanation of our pipeline and the result returned are documented [here](doc/pipeline.md).

## Demo

We provide a demo showcasing a Redmine integration of our system.

### pre-configured demo

For quick testing purpose, this version of the demo is already configured.

Clone this repository with his submodules.

```bash
git clone https://git.rnd.alterway.fr/overboard/openreq/oraw3_missing-features
cd oraw3_missing-features
```

Copy `SentiStrengthCom.jar` in `oraw2_issue-weight/scikit-sentistrength`. Note that sentistrength.jar is not included in this repository since it's proprietary software, please refer to [this](http://sentistrength.wlv.ac.uk/) site.

```bash
cp ??? oraw2_issue-weight/scikit-sentistrength/SentiStrengthCom.jar
```

Log in to our GitLab’s Container Registry:

```bash
docker login hub.rnd.alterway.fr
```

Launch the demo

```bash
docker-compose up -d
```

From there you should be able to connect to [Redmine](localhost:3000).

The default username is `admin` and the password is `password`.

You can create a new issue in the preconfigured project "test1". Issue samples are provided in the samples directory.

The newly created issues are automatically classified with 3 fields:

- Category: Demand, Anomaly, Human
- Urgence: Basse, Normale, Haute
- ponderation: The higher is the priority

### From raw images

Launch the demo with the following command instead:

```bash
docker-compose -f docker-compose.raw.yml up
```

Create the initial configuration of your Redmine instance, please refer to [redmine.org](https://redmine.org) for additional documentation.

Be sure to add 3 custom field and to activate them in the concerned projects:

- Category a list with 3 possible values Demand, Anomaly and Human
- Urgence a list with 3 possible values Basse, Normale and Haute
- ponderation a float

Then configure the ponderation plugin ([README](redmine-ponderation-plugin/README.md)).

In the qualification plugin map the custom fields with the oraw3 service:

```text
Categorie   http://oraw3:8081/tracker
Urgence     http://oraw3:8081/urgence
```

Finally, activate both `auto qualification` and `auto ponderation` modules in the projects of your choice.


## License

Free use of this software is granted under the terms of the EPL version 2 (EPL2.0).
