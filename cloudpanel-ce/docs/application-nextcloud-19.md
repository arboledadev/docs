---
id: application-nextcloud-19
title: Nextcloud 19
sidebar_label: Nextcloud 19
---

import useBaseUrl from '@docusaurus/useBaseUrl';

On this page, we explain step by step how to setup **Nextcloud 19** with **CloudPanel**.

## Installation

In the following example we will setup **Nextcloud 19** under the domain ***www.domain.com***.

### Preparation

Before we can start with the installation of **Nextcloud 19**, we need to create an [SSH User](users#adding-a-user), a [Database](databases#adding-a-database) <br />
and a [Domain](domains#adding-a-domain).

When you [Add the Domain](domains#adding-a-domain), make sure to select the **Nextcloud 19 Vhost Template** and the right **PHP Version**.

<img class="border" src={useBaseUrl('img/v1/applications/nextcloud-19/new_domain.png')} /> <br /><br />

### Installation

To install **Nextcloud 19** do the following steps:

1. [Login via SSH](users#ssh-login) to the server e.g. with **john-ssh** and go to the users **tmp** directory:

```
cd ~/tmp
```

2. Download and extract the latest **Nextcloud 19** version.

```
curl -sLo nextcloud-19.zip https://download.nextcloud.com/server/releases/nextcloud-19.0.1.zip && unzip nextcloud-19.zip -d nextcloud-19
```

:::caution Latest Version
You find the latest version on github: [https://github.com/nextcloud/server/releases](https://github.com/nextcloud/server/releases)
:::

3. Move files to the **htdocs** directory of the domain:

```
cp -R nextcloud-19/nextcloud/* /home/cloudpanel/htdocs/www.domain.com/
```

4. Reset permissions.

```
cd /home/cloudpanel/htdocs/
clpctl system:permissions:reset www.domain.com 775
```

5. Clean up the **tmp** directory.

```
rm -rf ~/tmp/*
```

6. Open your domain in the browser and enter your **admin account** and **database credentials**.

Click on the button **Finish setup** to install **Nextcloud 19**.

<img class="border" src={useBaseUrl('img/v1/applications/nextcloud-19/setup.png')} />

7. Done! **Nextcloud 19** is now installed.

<img class="border" src={useBaseUrl('img/v1/applications/nextcloud-19/nextcloud.png')} />



