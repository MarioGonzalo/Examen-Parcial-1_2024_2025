# Examen-Parcial-1_2024_2025

# Parte I: Conceptos y Teoría

## 1. El Mural de las Siete Capas

Te adentras en la sala principal del templo y descubres un gran mural compuesto por siete franjas horizontales superpuestas, decoradas con símbolos y jeroglíficos. Cada franja representa un nivel diferente en un ritual de comunicación. Los sabios de esta civilización entendían que un mensaje debía pasar por varias etapas desde su origen hasta su destino, refinándose o traduciendo su forma en cada nivel de la pirámide comunicativa.

**Pregunta:** ¿Qué representa el mural de las siete capas en términos de las redes de comunicación modernas? Identifica brevemente cada capa y explica cómo se relaciona este antiguo “modelo” con el proceso de comunicación de datos actual.

**Respuesta:** Tras inspeccionar la sala central me topé con estas siete franjas, este antiguo modelo me recordó a uno que empleamos en la actualidad, el modelo OSI, al igual que estas siete franjas de jeroglíficos el modelo OSI también tiene siete capas, la capa física, la capa de enlace de datos, la capa de red, la capa de transporte, la capa de sesión, la capa de presentación y la capa de aplicación. Me pareció extraño porque al traducir los jeroglíficos me di cuenta de que las siete capas de este modelo antiguo hacían lo mismo que sus iguales en nuestro modelo:
- La primera capa, la **capa física** se encargaba de transmitir los datos a través de bits por medios físicos
- La segunda capa, la **capa de enlace de datos** convertía estos datos en una línea de comunicación sin errores y fragmentaba las señales en tramas de datos
- Les seguía la **capa de red** que se encargaba de enrutar los paquetes tratando de encontrar la mejor ruta para estos y evitando congestiones
- La cuarta era la **capa de transporte** que abstraía a las capas superiores de los cambios que podían sufrirse en las capas inferiores actuando como una especie de mediador. Empleando los protocolos TCP/UDP se encargaba de proporcionar una comunicación confiable.
- La siguiente era la **capa de sesión** que manejaba la creación, mantenimiento y terminación de las sesiones entre aplicaciones.
- La número seis era la **capa de presentación** a la que se le confíaba la misión de traducir los datos a un formato que entendiera la última capa basándose en estructuras de datos abstractas.
- Por último la **capa de aplicación** hacía de mediadora entre el usuario y la red mediante una interfaz.

Tras confirmar que estas siete capas eran iguales al modelo OSI de la actualidad continué buscando más pistas sobre esta avanzada civilización. Me percaté de que una baldosa de la pared de la sala central sobresalía, lo apreté y se abrió una puerta escondida dándome paso a una cámara oculta.

## 2. Los Dos Pergaminos del Mensajero
En una cámara oculta encuentras dos pergaminos polvorientos. El primero describe el Ritual del Mensajero Confiable: antes de entregar un mensaje, el mensajero realiza un saludo de tres pasos con el receptor para asegurarse de que ambos estén listos, luego entrega el mensaje y espera una confirmación de recibido. Si la confirmación no llega, reintenta el envío. El segundo pergamino narra el Ritual del Mensajero Veloz: un mensajero que sale disparado a entregar mensajes sucesivos sin aviso previo ni asegurarse de la recepción, cubriendo la mayor distancia en el menor tiempo, aunque a veces los mensajes se pierdan en el camino.

**Pregunta:** Interpreta los dos rituales descritos. ¿A qué protocolos de comunicación actuales equivalen el mensajero confiable y el mensajero veloz? Compara sus características, explicando las ventajas y desventajas de cada enfoque en redes modernas.

**Respuesta:** Tras adentrarme cautelosamente en esta sala secreta pude vislumbrar en la oscuridad del habitáculo dos pergaminos, los dos hablaban de dos rituales que empleaba esta civilización para entregar mensajes. Estos parecían muy similares a algo que existia en la realidad, los protocolos TCP y UDP que, al igual que en los rituales, tenían diferentes puntos fuertes pero a su vez otras debilidades:

- El Ritual del Mensajero Confiable o protocolo TCP siempre se aseguraba de establecer una conexión con el receptor del mensaje, se encargaba de ordenar los mensajes y si no le llegaba confirmación del receptor volvía a mandar los mensajes para asegurarse de que el paquete era recibido.

- Por el otro lado está el Ritual del Mensajero Veloz o protocolo UDP, este no se aseguraba de mantener una conexión con el receptor resultando en una potencial pérdida de paquetes pudiendo perder información por el camino pero a cambio brindaba mucha más velocidad por lo que se usaba para cuando se mandaban muchos paquetes y no importaba que se perdieran algunos.

Tras terminar de descifrar estos pergaminos antiguos vi un pasillo a la derecha en el que decidí internarme buscando otro indicio de esta misteriosa civilización

## 3. El Enigma de las Subredes
Avanzando por un pasillo, encuentras una losa de piedra con inscripciones que parecen ser direcciones numéricas. Una inscripción cuenta: "Nuestro reino digital tenía la dirección sagrada 192.168.50.0. Los cuatro grandes gremios de la ciudad exigían su propio distrito en la red, todos de igual tamaño". Junto a esto, ves un diagrama borroso de algo que parecen ser subredes emanando de la dirección principal, cada una con su propio identificador.

**Pregunta:** Descifra el enigma de la losa. Si la antigua red usaba la dirección 192.168.50.0 como base y necesitaba dividirse en 4 subredes de igual tamaño (una para cada gremio), ¿qué máscara de subred habrían utilizado los antiguos para lograrlo? ¿Cuántas direcciones de host (utilizables) tendría cada subred resultante? Explica brevemente tu razonamiento al calcular la máscara.

**Respuesta:** Al adentrarme en este pasillo me encontré con una losa iluminada por un agujero en el techo del templo, al leerla me sorprendí ya que vi que este reino empleaba una dirección sagrada muy parecida a nuestras IPs, vi que habían cuatro gremios así que no tardé en investigar y ponerme a calcular cómo serían estas subredes en la actualidad para ver si coincidían con las de este grabado.

Tenía primero que calcular cuántas direcciones posibles de host habían, vi que al empezar por 192 entraba en el rango de ips de clase C por lo que usaría una máscara de subred 255.255.255.0 dejándonos únicamente el último octeto para hosts, es decir, $2^8 = 256$ direcciones de host. Sabiendo que tenemos 4 gremios tenemos que repartir todas estas direcciones entre estos cuatro gremios por lo que les quedaban 64 direcciones de host a cada uno. Como cada gremio necesitaba su propia dirección de broadcast y su propia dirección de red les quedaban 62 direcciones para repartir entre todos los dispositivos del gremio.

Usamos una máscara /26 (24 bits originales + 2 para subredes):

**Máscara /26:** 255.255.255.192 <br>
**Incremento:** 256 - 192 = 64  
Cada subred tendrá bloques de **64 IPs**

| Subred | Rango de IPs                      | Dirección de red   | Broadcast         |
|--------|-----------------------------------|---------------------|-------------------|
| 1      | 192.169.50.1 - 192.169.50.62      | 192.169.50.0        | 192.169.50.63     |
| 2      | 192.169.50.65 - 192.169.50.126    | 192.169.50.64       | 192.169.50.127    |
| 3      | 192.169.50.129 - 192.169.50.190   | 192.169.50.128      | 192.169.50.191    |
| 4      | 192.169.50.193 - 192.169.50.254   | 192.169.50.192      | 192.169.50.255    |


Tras hacer todos estos cálculos lo comparé con el grabado y, efectivamente, eran iguales aumentando todavía más mi curiosidad por esta civilización por lo que me decidí a seguir investigando, continué por el pasillo llegando a una misteriosa encrucijada.

## 4. La Encrucijada de las Rutas
Llegas a una encrucijada dentro de las ruinas: cuatro caminos diferentes se extienden hacia distintas aldeas en los alrededores de la ciudad antigua. En el centro, un tótem tallado muestra flechas apuntando hacia cada camino, con inscripciones de destinos y distancias. Notas que algunas flechas parecen fijas e inmutables (talladas en la piedra), mientras que otras son piezas móviles que pudieron reorientarse si se abría o cerraba algún camino en el pasado. Este tótem se asemeja a un antiguo dispositivo de enrutamiento que dirigía el tráfico de datos por el camino adecuado.

**Pregunta:** ¿Qué concepto moderno de redes representa el tótem con flechas de la encrucijada? Explica qué es una tabla de enrutamiento y cómo funciona en un router actual. Además, interpreta la diferencia entre las flechas talladas en piedra y las flechas móviles en términos de enrutamiento estático vs. enrutamiento dinámico en redes.

**Respuesta:** Al llegar a la encrucijada me encontré un tótem con flechas que señalaban a diferentes caminos, empecé a inspeccionar viendo que había algunas flechas fijas pero otras eran móviles, me pareció muy extraño pero como en las anteriores investigaciones traté de compararlo con algo de la actualidad, entonces todo cuadró, este totem es igual que un router por lo que empecé a analizarlo parte por parte para ver sus similitudes con este dispositivo.

Vi que tenía inscrito una lista de aldeas, lo que me recordó a la tabla de enrutamiento de los routers actuales que son básicamente una lista de las direcciones a los que puede redirigir los paquetes ese router. Cuando llega un paquete a un router este calcula la ruta más rápida y óptima hasta su destino y lo redirige hacia allí. Luego vi las flechas movibles y solidas y me recordó al enrutamiento dinámico y al estático.

**Enrutamiento Estático**

El cual está definido manualmente por un administrador

Ventajas:

- Simplicidad: útil en redes pequeñas o con topologías fijas.

- Control total: el administrador decide exactamente qué rutas se usan.

- Menor carga en el router: no hay procesos que calculen rutas dinámicamente.

Desventajas:

- No se adapta a cambios: si una ruta cae, el router no puede redirigir el tráfico automáticamente.

- Escalabilidad limitada: en redes grandes, mantener rutas manuales es inviable.

**Enrutamiento Dinámico**

El cual aprende rutas automáticamente

Ventajas:

- Adaptación automática: si una ruta falla, se elige otra disponible.

- Escalable: ideal para redes grandes y complejas.

- Menor mantenimiento manual: los cambios en la red se propagan solos.

Desventajas:

- Mayor uso de CPU y memoria.

- Mayor complejidad en configuración y monitoreo.

- Puede ser vulnerable a errores o ataques si no se protege correctamente.

Tras terminar de investigar este tótem le indiqué que quería ir a la salida y este me redirigió a un camino por el que avancé hasta que llegué a la última sala de este templo.

## 5. El Guardián de la Máscara Única
En la última sala del templo, frente a la salida, te encuentras con la estatua de un guardián con dos caras. Según una leyenda grabada en la base, este guardián protegía la ciudad oculta de los forasteros. Cuando un mensajero salía de la ciudad, el guardián reemplazaba su máscara por la suya propia, de modo que, para el mundo exterior, todos los mensajes parecían venir únicamente del guardián. Al regresar la respuesta, el guardián recordaba qué máscara original correspondía a cada mensaje y reenviaba la respuesta al habitante correcto dentro de la ciudad. Gracias a este ardid, la ciudad pudo ocultar la identidad de sus miembros y usar un único rostro para todas sus comunicaciones externas.

**Pregunta:** ¿Qué técnica de redes moderna se refleja en la leyenda del Guardián de la Máscara? Nombra y describe brevemente este mecanismo, explicando cómo permite que múltiples dispositivos internos de una red compartan una única identidad (direcación) al comunicarse con el exterior, y menciona dos beneficios que brinda esta estrategia a las redes actuales.

**Respuesta:** Tras recorrer el pasillo que me indicó el tótem router llegué a la última sala del templo, en ella me encontré a una estatua extraña con dos caras, a las que se parecía poder encajar máscaras, me percaté de un grabado en la base de la estatua y lo entendí todo, ya me sabía el truco, esto correspondía con algo de la actualidad, y esto me sonaba mucho al firewall así que empecé a hacer lo de siempre, comparar las características de esto con las del firewall:

El firewall es un sistema de seguridad de red diseñado para monitorear y controlar el tráfico de datos entre redes, permitiendo o bloqueando el acceso según una serie de reglas de seguridad predefinidas. Su función principal es proteger las redes internas de accesos no autorizados provenientes de redes externas, como Internet permitiendo que mútiples dispositivos internos compartan una única dirección gracias al NAT que cuando un dispositivo interno envía una solicitud a un servidor externo, el firewall cambia la dirección IP de origen de esa solicitud por la IP pública de la red dotando de una mayor seguridad a los dispostivos del interior.

Después de resolver este último misterio me dirigí a la salida tras esta aventura.


# Parte II: Práctica con Cisco Packet Tracer
En la segunda parte de tu misión, tu rol como arqueólogo de redes pasa de la teoría a la acción. Deberás emplear tus herramientas (¡tu látigo es ahora Cisco Packet Tracer!) para resucitar la infraestructura de red de esta civilización. Se te presentan dos escenarios prácticos, integrados en la narrativa, donde configurarás routers, switches y PCs para resolver los misterios y restaurar la comunicación entre los fragmentos de la ciudad perdida.

Cada ejercicio está envuelto en el contexto ficticio, pero requiere pasos técnicos reales. Lee atentamente la historia de cada desafío, identifica los requisitos de red y constrúyelo en Packet Tracer. Importante: Documenta cada ejercicio y guarda tu topología funcionando, pues entregarás las pruebas de tu reconstrucción.

## Ejercicio 1: La Ruta Perdida entre Dos Reinos
Tras salir del templo, el diario del aventurero te conduce a los restos de dos ciudades hermanas separadas por un vasto desierto. Según los relatos, en la antigüedad estas ciudades (reinos) estaban conectadas por la Ruta Sagrada de Datos, un enlace de comunicación que permitía compartir conocimiento y recursos. Con el tiempo, la ruta cayó en el olvido y las ciudades quedaron incomunicadas, como islas aisladas. Tu misión es reconstruir esa ruta perdida para volver a unir las redes de ambas ciudades.

En términos actuales, cada ciudad tiene su propia red local (subred) y disponía de un router en su gran torre de comunicaciones. Entre ambas torres existía un enlace directo (un cable histórico que unía las dos ciudades). También se encontraban switches en las plazas centrales de cada ciudad, conectando los ordenadores (PCs) de los habitantes. Para restaurar la conexión, tendrás que configurar apropiadamente los dispositivos de ambas urbes y el enlace entre ellas.

![Image](https://github.com/user-attachments/assets/b9c75f8e-2bcf-479c-bc1a-9b8e87550a27)

En este ejercicio hay 4 ordenadores conectados a dos switches Cisco 2960 que a su vez están conectados a dos routers Cisco 2901

**Tabla de IPs**

### Red 1: Subred 192.168.10.0/24

| Dispositivo     | IP             | Descripción           |
|-----------------|----------------|------------------------|
| Ordenador 1     | 192.168.10.2   | PC conectado al switch |
| Ordenador 2     | 192.168.10.3   | PC conectado al switch |
| Switch          | 192.168.10.1   | Switch de red local    |

---

### Red 2: Subred 192.168.20.0/24

| Dispositivo     | IP             | Descripción           |
|-----------------|----------------|------------------------|
| Ordenador 1     | 192.168.20.2   | PC conectado al switch |
| Ordenador 2     | 192.168.20.3   | PC conectado al switch |
| Switch          | 192.168.20.1   | Switch de red local    |

Estos dos switches están conectados entre si por un cable cruzado permitiendo la comunicación entre routers

## Ejercicio 2: La Ciudad de las Redes Aisladas
Tras conectar las dos ciudades, te internas en las ruinas de la gran metrópolis central. Descubres que esta ciudad antigua estaba dividida en facciones o gremios, cada uno operando en su propio “canal sagrado” de comunicaciones para evitar interferencias con los otros. A pesar de compartir la misma infraestructura física (todas las guildas estaban en la misma ciudad y conectadas por los mismos caminos), utilizaron alguna forma de segmentación para que sus mensajes viajaran aislados, como si existieran redes paralelas invisibles dentro de la misma urbe. Solo en la Gran Torre Central (el edificio del consejo, equivalente a un router moderno) se unían estas comunicaciones, permitiendo el intercambio de mensajes entre gremios cuando era necesario, bajo supervisión.

En tecnología de redes actual, lo que has descubierto es una ciudad implementada con VLANs (Redes Locales Virtuales) para separar el tráfico de cada gremio, y un enrutamiento router-on-a-stick (router con subinterfaces) en la torre central para interconectarlas de forma controlada. ¡Tu tarea es revivir esta arquitectura de red segmentada!

![Image](https://github.com/user-attachments/assets/bcb429d4-788e-4951-b4e0-d9970e367d7a)

En este ejercicio habrá 4 dispositivos, dos para cada gremio, un switch Cisco 2960 para poder soportar las VLANs necesarias y trunking y un router Cisco 2811

Los cuatro pcs estarán unidos al switch central, estos tendrán una dirección ip de 192.168.[numero de VLAN].[2-3] dependiendo de la VLAN que estén (10 o 20) tendrán una dirección de IP diferente y terminarán en 2 o 3 para diferenciarlos. El switch tiene 4 ordenadores conectados, dos de la VLAN de arquitectos, la 10 y dos de la VLAN de escribas, la 20, todos estos puertos serán de access y tendrán la VLAN específica para cada ordenador que está conectado, el único puerto que no es de access es en el que se conecta al router central, que es de trunk, esta conexión está formada por un cable cruzado con este router, el router se encargará de distribuir los paquetes entre las capas, si no las capas estarán aisladas entre ellas y no podrán pasar mensajes de una VLAN a otra. 

**Tabla de IPs**

### Vlan 10

| Dispositivo     | IP             | Descripción           |
|-----------------|----------------|------------------------|
| Ordenador 1     | 192.168.10.2   | PC conectado al switch |
| Ordenador 2     | 192.168.10.3   | PC conectado al switch |
