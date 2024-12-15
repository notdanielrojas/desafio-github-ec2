# Despliegue en EC2 con GitHub Actions

## Descripción
Este repositorio contiene los archivos necesarios para automatizar la creación y gestión de una instancia EC2 en AWS utilizando GitHub Actions. El objetivo del desafío es familiarizarse con los conceptos de creación y gestión de instancias EC2, configuración de seguridad y acceso mediante SSH, configuración de redes en VPC, y el uso de AMIs personalizadas.

## Requerimientos
1. **Creación y gestión de instancias EC2**:
   - Crear una instancia EC2 en AWS usando GitHub Actions.
   - El flujo de trabajo debe incluir la creación de la instancia, la configuración de los parámetros básicos y su inicio.

2. **Tipos de instancias y casos de uso**:
   - Definir el tipo de instancia que se utilizará (por ejemplo, t2.micro, t3.medium, etc.) y justificar la elección según el caso de uso propuesto (ejemplo: desarrollo, pruebas, producción).

3. **Seguridad y acceso**:
   - Configurar un grupo de seguridad para la instancia EC2, asegurando que solo se permita el acceso SSH a través de una clave privada.
   - Asegurarse de que la clave SSH sea correctamente generada y gestionada en el flujo de trabajo de GitHub Actions.

4. **Configuración de redes y VPC**:
   - Asegurarse de que la instancia EC2 esté lanzada dentro de una VPC adecuada y de que la configuración de subredes y rutas sea correcta.

5. **Uso de AMIs personalizadas**:
   - Crear una imagen de máquina de Amazon (AMI) personalizada basada en la instancia EC2 creada, asegurando que pueda ser utilizada para lanzar nuevas instancias con configuraciones similares en el futuro.

## Justificación de decisiones
- **Elección del tipo de instancia**: Se seleccionó `t2.micro` para el despliegue, ya que este tipo de instancia ofrece un equilibrio adecuado entre rendimiento y costo para pruebas y desarrollo. Justificación: Se buscó minimizar costos mientras se mantenía una capacidad de cómputo suficiente para las tareas previstas, como pruebas y despliegues de aplicaciones en desarrollo.

- **Configuración de seguridad**:
  - Se configuró un grupo de seguridad que solo permite el acceso SSH desde una IP específica. Justificación: Esta configuración es crucial para proteger la instancia de accesos no autorizados, garantizando que solo los usuarios con permisos específicos puedan conectarse.
  - La gestión adecuada de la clave SSH fue fundamental para asegurar la comunicación segura entre la instancia y el usuario. Justificación: Utilizar una clave privada bien gestionada minimiza el riesgo de accesos no autorizados y permite una comunicación segura.

- **Configuración de redes y VPC**:
  - La instancia fue lanzada dentro de una VPC con una configuración de subredes y rutas que permitían una conectividad adecuada entre las instancias y con el exterior. Justificación: Esta configuración es vital para asegurar que las instancias puedan comunicarse entre sí y con otros recursos en la misma VPC, así como con el mundo exterior de manera segura.

- **Uso de AMIs personalizadas**:
  - Se creó una AMI personalizada basada en la instancia inicial para permitir la rápida creación de nuevas instancias con las mismas configuraciones. Justificación: Esto facilita la escalabilidad de la infraestructura y asegura que las instancias creadas en el futuro tengan las mismas optimizaciones y configuraciones que la instancia inicial.
