A) Describa brevemente a su cliente, Artemis Financial, y sus requisitos de software. 
¿Quién era el cliente y qué necesidad buscaba atender la empresa?

Artemis Financial es una empresa de consultoría que desarrolla planes financieros personalizados para sus clientes. 
La empresa requería implementar niveles de seguridad en su sistema para cerciorarse de que las comunicaciones mantuvieran 
su integridad y verificar que los datos no fueran manipulados en tránsito. Estos requisitos son especialmente necesarios 
debido a la naturaleza de la empresa y los tipos de datos que maneja de sus clientes, siendo de índole financiera y personal. 

B) ¿Qué decisiones acertadas tomó al identificar las vulnerabilidades de seguridad en el software del cliente? 
¿Por qué es importante desarrollar código seguro? ¿Qué aporta la seguridad del software al desempeño general de una empresa?

El proceso de análisis para identificar las vulnerabilidades en el código fuente que se proveyó para la actividad fue honestamente
más complicado de lo que esperaba. Aunque tuve varios errores, principalmente al momento de hacer los análisis manuales del código, 
considero que un gran acierto es buscar deliberadamente en el código alguna implementación insegura en todas las secciones donde hayan
funciones que reciban input de algún tipo que provenga del usuario. Incluso cuando las librerías introducen un gran número de 
vulnerabilidades de manera inadvertida, el principal indicador que determinará si realmente incrementan el riesgo para nuestro programa
es cómo las funciones de dichas librerías se implementen en el código. Más puntualmente para esta evaluación, se tomó la decisión acertada
de especificar explícitamente el uso del algoritmo moderno SHA-256 mediante la clase MessageDigest, evitando algoritmos obsoletos e 
inseguros como MD5 o SHA-1.

C) ¿Qué parte del proceso de evaluación de vulnerabilidades le resultó más difícil o más útil?

La parte más difícil para mí en el proceso de evaluación de vulnerabilidades fue el análiis manual del código fuente, 
pues si bien tengo un entendimiento aceptable de los tipos de vulnerabilidades más comúnes como ataques Man In The Middle, DoS, 
buffer overload, etc. y herramientas adecuadas para robustecer la seguridad de un sistema en el proceso de tránsito de datos, aún
tengo dificultad en analizar si una función implementada en el cóigo es arriesgada. Otro aspecto que se me continúa dificultando 
bastante es navegar la base de datos de vulnerabilidades CVE, y en algunos casos hallar compatibilidad con Maven para ejecutar el 
Dependency-Check, llegando a modificar mi archivo pom.xml una infinidad de veces antes de lograr un build exitoso. 

D) ¿Cómo reforzó las capas de seguridad? En el futuro, ¿qué recursos emplearía para evaluar vulnerabilidades y seleccionar las técnicas 
de mitigación más adecuadas?

Las capas de seguridad se reforzaron mediante la configuración de certificados digitales para habilitar comunicaciones cifradas utilizando 
SSL/TLS en el servidor. Asimismo, se integró el uso de SHA-256 para generar sumas de comprobación que permiten verificar la 
integridad de los datos y detectar posibles modificaciones. También se ejecutaron análisis estáticos con OWASP Dependency-Check para 
identificar dependencias vulnerables y evaluar posibles riesgos de seguridad en las librerías del proyecto. También recomendaría integrar 
OWASP Dependency-Check en una pipeline de CI/CD para automatizar el análisis de dependencias y permitir que un ingeniero de calidad revise 
las vulnerabilidades detectadas antes de autorizar el despliegue de la aplicación.


E) ¿Cómo comprobó que el código y la aplicación siguieran siendo funcionales y seguros? Después de refactorizar el código, 
¿cómo verificó que no se hubieran introducido nuevas vulnerabilidades?

Primero, se realizó un análisis manual del código tomando en cuenta los requisitos de la aplicación, con especial énfasis en el manejo de
entradas para verificar si existía algún proceso de sanitización que ayudara a prevenir la introducción de datos maliciosos. Posteriormente, 
para asegurar que las modificaciones realizadas no introdujeran vulnerabilidades adicionales, se compararon los reportes de OWASP 
Dependency-Check generados antes y después de los cambios en el código, con el propósito de identificar posibles diferencias en las 
dependencias vulnerables detectadas.

F) ¿Qué recursos, herramientas o prácticas de codificación utilizó que podrían serle de utilidad en trabajos futuros?

Entre los recursos y prácticas de codificación que considero útiles para futuros proyectos se encuentran el uso del algoritmo 
criptográfico SHA-256, la configuración de protocolos de comunicación segura HTTPS/SSL/TLS y la implementación de herramientas 
de análisis automatizado de dependencias, como OWASP Dependency-Check. Asimismo, considero importante familiarizarme con las buenas 
prácticas recomendadas por entidades como el NIST y la OWASP, pues proporcionan guias para desarrollar software más seguro. 
Finalmente, considero que la base de datos de CVE es un recurso invaluable que me permitirá investigar vulnerabilidades conocidas y, 
sobre todo, mantenerme actualizada en un campo donde los estándares de seguridad, las amenazas y las técnicas de mitigación evolucionan 
constantemente.

G) Con frecuencia, los empleadores solicitan ejemplos de trabajos exitosos para valorar aptitudes, conocimientos y experiencia. 
Con base en esta actividad, ¿qué evidencia podría presentar a futuros empleadores?

Como evidencia de mis conocimientos y habilidades para futuros empleadores, cuento con dos entregables completos en los que 
realizo análisis de seguridad mediante documentos relativamente extensos, de alrededor de 12 páginas cada uno. Estos documentos 
incluyen análisis técnicos y justificaciones de las decisiones tomadas durante el proceso de desarrollo, así como capturas de 
pantalla del código refactorizado funcionando correctamente y sin errores, reportes comparativos de OWASP Dependency-Check generados 
antes y después de las modificaciones para demostrar el control de las dependencias vulnerables y evidencias de la generación exitosa 
de sumas de comprobación mediante SHA-256. Considero que estos entregables representan una oportunidad para demostrar mi capacidad de 
analizar código, identificar posibles vulnerabilidades y aplicar técnicas de mitigación. Adicionalmente, los conocimientos técnicos 
adquiridos me serán de utilidad durante futuras entrevistas técnicas, especialmente en aquellas donde se solicite explicar mi razonamiento 
y justificar mis decisiones en lugar de presentar únicamente un producto terminado. Esto me permitirá profundizar en las decisiones de 
diseño que tomé teniendo en cuenta la seguridad de la aplicación y explicar cómo las herramientas y prácticas utilizadas contribuyen a 
desarrollar software más seguro.

















