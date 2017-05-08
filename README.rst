ProductAI SDK for Python
========================

.. image:: https://travis-ci.org/MalongTech/productai-python-sdk.svg?branch=master
    :target: https://travis-ci.org/MalongTech/productai-python-sdk

.. image:: https://badge.fury.io/py/productai.svg
    :target: https://badge.fury.io/py/productai

.. image:: https://codeclimate.com/github/MalongTech/productai-python-sdk/badges/gpa.svg
   :target: https://codeclimate.com/github/MalongTech/productai-python-sdk
      :alt: Code Climate

ProductAI® SDKs enable using ProductAI® APIs easily in the programming languege of your choice. You can use our Python SDK to send image queries and maintain your datasets.

installation
----

.. code-block:: bash

    $ pip install productai

Quick start
--------

Add single image to image set
~~~~~~~~

.. code-block:: python

    from productai import Client

    cli = Client(access_key_id, access_key_secret)
    api = cli.get_image_set_api(image_set_id)
    resp = api.add_image(url, meta, tags='cartoon|square')


Batch add images to image set
~~~~~~~

.. code-block:: python

    from productai import Client

    cli = Client(access_key_id, access_key_secret)
    api = cli.get_image_set_api(image_set_id)
    with open('images.csv') as f:
        res = api.add_images_in_bulk(f)


Remove images from image set
~~~~~~~

.. code-block:: python

    from productai import Client

    cli = Client(access_key_id, access_key_secret)
    api = cli.get_image_set_api(image_set_id)
    with open("images.csv") as f:
        resp = api.delete_images_in_bulk(f)



Search images
~~~~

.. code-block:: python

    from productai import Client

    cli = Client(access_key_id, access_key_secret)
    api = cli.get_image_search_api(service_id)

    # query by url of image
    resp = api.query(image_url)

    # or query by local image
    with open("fashion.jpg") as f_image:
        resp = api.query(f_image)

    # Specifies the maximum number of results, defaults is 20
    resp = api.query(image_url, count=10)



Use other service
~~~~~~

.. code-block:: python

    from productai import Client

    cli = Client(access_key_id, access_key_secret)
    api = cli.get_api(service_type, service_id)
    resp = api.query(image_url)

e.g:

.. code-block:: python

    from productai import Client

    access_key_id, access_key_secret = 'your access key', 'your secret'
    image_url = 'an image url'
    service_type, service_id = 'public', '_0000030'
    cli = Client(access_key_id, access_key_secret)
    api = cli.get_api(service_type, service_id)
    resp = api.query(image_url)



安装
----

.. code-block:: bash

    $ pip install productai

快速入门
--------

添加图片到图集
~~~~~~~~

.. code-block:: python

    from productai import Client

    cli = Client(access_key_id, access_key_secret)
    api = cli.get_image_set_api(image_set_id)
    resp = api.add_image(url, meta, tags='卡通|四方')


批量添加图片到图集
~~~~~~~

.. code-block:: python

    from productai import Client

    cli = Client(access_key_id, access_key_secret)
    api = cli.get_image_set_api(image_set_id)
    with open('images.csv') as f:
        res = api.add_images_in_bulk(f)


删除图集中的图片
~~~~~~~

.. code-block:: python

    from productai import Client

    cli = Client(access_key_id, access_key_secret)
    api = cli.get_image_set_api(image_set_id)
    with open("images.csv") as f:
        resp = api.delete_images_in_bulk(f)


搜索图片
~~~~

.. code-block:: python

    from productai import Client

    cli = Client(access_key_id, access_key_secret)
    api = cli.get_image_search_api(service_id)

    # 用图片URL查询
    resp = api.query(image_url)

    # 或者直接上传本地图片查询
    with open("fashion.jpg") as f_image:
        resp = api.query(f_image)

    # 指定查询结果数量上限，默认为 20
    resp = api.query(image_url, count=10)



使用其他服务
~~~~~~

.. code-block:: python

    from productai import Client

    cli = Client(access_key_id, access_key_secret)
    api = cli.get_api(service_type, service_id)
    resp = api.query(image_url)

例如: 

.. code-block:: python

    from productai import Client

    access_key_id, access_key_secret = '你的 access key', '你的 secret'
    image_url = '图片 url 地址'
    service_type, service_id = 'public', '_0000030'
    cli = Client(access_key_id, access_key_secret)
    api = cli.get_api(service_type, service_id)
    resp = api.query(image_url)
