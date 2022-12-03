# Proyecto
## Cassandra
### 1. Que es Apache Cassandra:

Apache Cassandra es un sistema de gestión de bases de datos (DBMS) de código abierto para bases de datos muy grandes, pero estructuradas. Gracias a la buena escalabilidad, estas bases de datos se pueden distribuir a diferentes clústeres, por lo que Cassandra no se encuentra unida a un único servidor.

### 2. Ventajas y desventajas:

#### Ventajas:

Alta disponibilidad, lo que es muy interesante para el sistema en los que una caída sea crucial.
Tolerancia a particiones y escalado.
Cantidad de recursos que se tienen disponibles.

#### Desventajas:

La conexión de nuevos nodos no es tarea fácil, ya que el mismo se tiene que poner de acuerdo con el resto, y esto conlleva un tiempo.
Debemos saber qué queries se van a ejecutar previamente, ya que al hacer SELECT sufre un poco debido a la manera en la que almacena los datos.

## Proceso de utilización:


### 1. Descargamos Apache Cassandra:

Descargamos Apache cassandra mediante el siguiente link:

```
https://www.apache.org/dyn/closer.lua/cassandra/4.0.7/apache-cassandra-4.0.7-bin.tar.gz
```

### 2. Creamos la ruta y definimos las variables de entorno:
[![image19.png](https://i.postimg.cc/x8CP1mxk/image19.png)](https://postimg.cc/hzkmCXqg)

### 3. Creamos una nueva variable:
[![image1.png](https://i.postimg.cc/xTD85yz5/image1.png)](https://postimg.cc/z37qXhpH)

### 4. Luego vamos a la carpeta de cassandra (bin)
[![image18.png](https://i.postimg.cc/pLFpzBpf/image18.png)](https://postimg.cc/68BWNnVq)

### 5. Escribimos CMD, en la ruta de dirección
[![image21.png](https://i.postimg.cc/ZKfrVjbX/image21.png)](https://postimg.cc/56CYtBFm)
[![image22.png](https://i.postimg.cc/h4sxtMdh/image22.png)](https://postimg.cc/JtytTNKW)

### 6. Escribimos cassandra para que se inicialice el servidor
[![image12.png](https://i.postimg.cc/8Pn6h5wS/image12.png)](https://postimg.cc/0bDjv9LW)

### 7. Luego descargamos interfaz grafica para poder trabajar con cassandra:
```
https://downloads.datastax.com/#cassandra-source-connector
```
Posteriormente, descargamos datastax Devcenter.
[![image2.png](https://i.postimg.cc/sf4PZstj/image2.png)](https://postimg.cc/z33HsZz6)

### 8. Abrimos devcenter
[![image8.png](https://i.postimg.cc/c4dmDrQt/image8.png)](https://postimg.cc/XXDdqN1n)

### 9.Creamos una conexión
[![image3.png](https://i.postimg.cc/KzgqywzK/image3.png)](https://postimg.cc/YGMf6XQk)

### 10. Damos a file new create new keyspace:
[![image4.png](https://i.postimg.cc/Hkph76SK/image4.png)](https://postimg.cc/tYM5KNGt)

### 11. Le damos a last y luego finish:
[![image6.png](https://i.postimg.cc/DZWDwmCw/image6.png)](https://postimg.cc/Fd4GPF5M)

### 12.Damos click al cuadradito para ver la tabla creada:
[![image7.png](https://i.postimg.cc/8zHxy2JN/image7.png)](https://postimg.cc/CRRv56sQ)

### 13. Creamos una tabla en nuestro keyspace TOPO1:
[![image10.png](https://i.postimg.cc/027TSM96/image10.png)](https://postimg.cc/VdLZQNr1)
[![image20.png](https://i.postimg.cc/kXrrDFP3/image20.png)](https://postimg.cc/4n12Sc3B)

Una aplicacion bastante interesante encontrada para Cassandra en Kubernetes se puede encontrrar en el siguiente enlace:
```
https://kubernetes.io/docs/tutorials/stateful-application/cassandra/
```

El cual muestra cómo ejecutar Apache Cassandra en Kubernetes. Cassandra, una base de datos, necesita almacenamiento persistente para proporcionar durabilidad de los datos (estado de la aplicación). En este ejemplo, un proveedor de semillas personalizado de Cassandra permite que la base de datos descubra nuevas instancias de Cassandra a medida que se unen al clúster de Cassandra.

Donde primero se debe servicio para cassandra sin encabezado utilizando un archivo .yaml, en este caso:
```
apiVersion: v1
kind: Service
metadata:
  labels:
    app: cassandra
  name: cassandra
spec:
  clusterIP: None
  ports:
  - port: 9042
  selector:
    app: cassandra
```

Obtenida directamente desde:
```
kubectl apply -f https://k8s.io/examples/application/cassandra/cassandra-service.yaml
```
En el codigo del sistema.
