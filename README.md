# [en] Mikrotik devices configuration

Configuration of two Mikrotik devices (hAP and hEX) step by step.

## Description

In this project we will make an installation using Mikrotik devices creating severall networks including Wifi. In this case, we will make four networks from which one will be wireless, one will conect both routers and the other two will be for the local network of each router using Ethernet cables (except two interfaces, number 5 of each router, that we will not modify so we can avoid having problems when we connect to the routers to configure them).

## Materials

* 3 Ethernet cables.
* hAP Mikrotik.
* hEX Mikrotik.
* PC for configuration.
* Mobilephone to check networks. 

## Physical instalation

* hEX device will be connected, from Internet interface, directly to the local network of the institute by an Ethernet cable directly to the switch of the classroom that, which in turn, it is connected to the classroom router.
* hAP device will be connected to the interface 2 of the hEX decive from the Internet interface through a Ethernet cable.
* The PC will be connected to the interface 5 of both of the devices to configure them.

## Configuration

To configure the devices, we will connect to the interface 5 of each router through an Ethernet cable from the PC.

### hEX

* We will start configuring the interface 2 creating a new bridge. This bridge will be called "bridge3".
* We are going to create another bridge, called "bridge2" and we will assign it to the interfaces 3 and 4.
* Now we will configure this bridges assigning them some gateways. The bridge 2 will have the gateway 192.168.10.1/24 and the bridge 3, 192.168.0.1/24.
* We will configure the DHCP for bridge 2. For this, we need to create a pool with the range 192.168.10.10-192.168.10.50.
* Once we have created the pool, we are going to create the DHCP server where we will assign the bridge 2, the pool created previously and we will put the DNS as 8.8.8.8 and the gateway 192.168.10.1.
* With all this, we will have finished the configuration of the hEX device.

### hAP

* We will start by configuring the Internet interface assigning it the ip 192.168.0.2/24.
* Next, we will create two bridges, being one of them "wifi", which will contain the interfaces Wlan5 and Wlan6, and the next will be the "bridge2" which will have the interfaces 2, 3 and 4.
* We will assign the gateways: 192.168.50.1/24 for "wifi" and 192.168.40.1/24 for "bridge2".
* We are going to create two pools to make two DHCP servers. One of the pools will be the Wifi one, with the range 192.168.50.10-192.168.50.50, and the other one will of the bridge 2, with the range 192.168.40.10-192.168.40.50.
* Once we have created both pools, we will create the two DHCP server and we will assign it its respective gateways and the DNS 8.8.8.8.
* For the Wireless network, we will change the name of the interface Wlan5 to "Mikrotik-Marcos" and the Wlan6 to "Mikrotik-Marcos5G".
* We are going to change the interfaces to "abridge" and we will assign them the default security method and we will set the password to "12345678".
* With all this, we will have finished the configuration of the hAP device.

---

# [es] Configuración de dispositivos Mikrotik 

Paso a paso de la configuración de dos dispositivos Mikrotik (hAP y hEX).

## Descripción

En este proyecto haremos una instalación con dispositivos Mikrotik creando varias redes incluyendo una Wifi. En este caso, haremos cuatro redes de las cuales una será inalámbrica, otra conectará ambos routers y las otras dos serán una de cada router a través de cables Ethernet (exeptuando dos interfaces, la 5 de cada router, que mantendremos sin modificar para que no surjan problemas a la hora de conectarnos para configurar dichos routers).

## Materiales

* 3 cables Ethernet.
* hAP Mikrotik.
* hEX Mikrotik.
* PC para configurar.
* Dispositivo móvil para realizar comprobaciones.

## Instalación física

* El dispositivo hEX se conecta, desde la interfaz de Internet, directamente a la red local del insitituto mediante un cable Ethernet directo al switch del aula que a su vez se conecta con el router de esta.
* El dispositivo hAP se conecta a la interfaz 2 del dispositivo hEX desde la interfaz de Internet mediante un cable Ethernet.
* El PC se conectará a la interfaz 5 de ambos dispotivos a medida que lo requeriramos para configurarlos.

## Configuración

Para configurar, accederemos a la interfaz 5 de cada router con un cable Ethernet desde el PC.

### hEX

* Empezaremos configurando la interfaz 2 creando un bridge nuevo para esta. Este bridge tendrá el nombre "bridge3".
* De paso, creamos otro bridge llamado "bridge2" y se lo asignaremos a las interfaces 3 y 4.
* Configuraremos estos bridges asignándoles puertas de enlace. El bridge 2 tendrá la puerta de enlance 192.168.10.1/24 y el bridge 3 tendrá la 192.168.0.1/24.
* Configuraremos ahora DHCP para el bridge 2. Para ello creamos un pool con el rango 192.168.10.10-192.168.10.50.
* Una vez creado el pool, creamos el servidor DHCP donde le asignaremos el bridge 2, el pool creado anteriormente y le ponemos como DNS el 8.8.8.8 y como puerta de enlace la 192.168.10.1.
* Con esto, ya habremos acabado la configuración del hEX.

### hAP

* Empezaremos configurando la interfaz de Internet asignandole la ip 192.168.0.2/24.
* A continuación, crearemos dos bridges siendo uno "wifi", el cual contendrá las interfaces Wlan5 y Wlan6, y el otro será "bridge2" el cual tendrá las interfaces 2, 3 y 4.
* Le asignaremos puertas de enlace: al "wifi" la 192.168.50.1/24 y al "bridge2" la 192.168.40.1/24.
* Creamos dos pools para hacer dos servidores DHCP. Un pool será el de la Wifi, con el rango 192.168.50.10-192.168.50.50, y el otro será del bridge 2, con el rango 192.168.40.10-192.168.40.50.
* Unas vez creados los pools, creamos los servidores DHCP y le asignamos sus respectivas puertas de enlace y el DNS 8.8.8.8.
* Para la red Wireless, cambiaremos el nombre de la interfaz Wlan5 a "Mikrotik-Marcos" y la Wlan6 a "Mikrotik-Marcos5G".
* Cambiamos estas interfaces a "abridge" y les asignamos el método de seguridad default al cual le cambiaremos la contraseña a "12345678".
* Con esto, finaliza la configuración del hAP.
