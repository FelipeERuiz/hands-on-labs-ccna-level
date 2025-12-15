# DHCP Client - GUIA
El objetivo de esta laboratorio es configurar DHCP server para que un cliente reciba una dirección ip por dhcp.
El escenario es el siguiente:

![[topologia.png]]
Lo que buscamos es que el router cliente **DMT-EDGE01** de **Dan Milli** reciba direccionamiento dinámico por dhcp.
Estos son los pasos realizados:
1. Definir un hostname a los equipos
	 En Router cliente:
	 ![[hostname-edge01.png]]
	 En Router ISP
	 ![[hostname-isp.png]]

2. Configurar direccionamiento estático al servidor DHCP (En este caso la direccion 200.1.1.1/24).
	
	[[static-ip-isp.png]]

3. Configurar router ISP como servidor dhcp.
	1. Definir las direcciones que se van a excluir (En este caso desde la direccion 1-9 no se van a entregar a los clientes dhcp).
		![[excluded-address.png]]
	2. Crear el pool dhcp.
		![[pool-name.png]]
	3. Definir la red al cual se le da las direcciones ip.
		![[network.png]]
	4. Definir quien es el gateway a ese pool.
		![[gateway.png]]
	5. Definir el servidor DNS.
		![[dns-server.png]]

4. Entrar al router cliente.
	1. Entrar a la interfaz he indicar que ese puerto recibirá direccionamiento por dhcp.
		![[client-dhcp.png]]

Podemos ver por el log que la interfaz g0/0/0 recibio una ip por DHCP, y si hacemos ping vemos que recibimos conectividad.

![[ping.png]]
Por ultimo guardamos la configuración en ambos routers.
![[ping.png]]
Asi concluye el laboratorio.


