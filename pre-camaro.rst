Preproduccion CAMARO
====================

``pre-camaro`` es servidor staging para GM.

Caracteristicas
---------------

+------------+------------+-----------+------------+-----------+
|            |    RAM     |    HDD    |    SO      |  kernel   |
+============+============+===========+============+===========+
| Tags       |    2GB     |   100GB   | SLES 11.2  |  x86_64   |
+------------+------------+-----------+------------+-----------+

.. warning::

    No tenemos Warnings.

Configuraciones
---------------

Configuraciones que se han realizado en el servidor.

http proxy
~~~~~~~~~~

Debido a que los servidores de GM no tienen salida a ningun lado, a menos de que se solicite
el alta de una regla para firewall indicando el motivo de su uso.
En la istalacion de paquetes para activar ambientes virtuales como ``virtualenv`` en python,
necesitamos salida a todo el segmento de ``pypi``.

Para tener salida hacia http(s) se ha configurado un proxy, en el cual utilizando un servidor
externo haremos llegar nuestras peticiones a ese servidor en donde se encargara de hacer proxy
utilizando ``squid``.

La configuracion puede utulizarce de varias formas, una de ellas es de forma general indicando
al sistema que utilice un proxy en peticiones http(s).

.. note::

    La IP del servidor que utilizaremos es: ``50.116.30.54`` el cual llamamos ``linode``

::

    $ export http_proxy='http://50.116.30.54:80'
    $ export https_proxy='http://50.116.30.54:80'

Con esto ya tenemos salida, podemos probar consultando cualquier stio web::

    $ curl google.com
    $ curl github.com


