# Piggy Wallet
## Getting Started

### Prerequisites

- Node.js (>=20) and npm installed (or pnpm)
- Git

### Quickstart

To get started, follow the steps bellow:

1. Install the dependencies using `npm`:

```bash
npm install
```

2. Run the `npm run dev` command to start the development server:

```bash
npm run dev
```

3. Visit `http://localhost:3000` to view your app.
Se hizo el deploy a Base Testnet.
Se implementó una base de datos para guardar datos de los usuarios, el mail y el address asociado. Si el usuario no se registra con mail, guardamos solo el address.
Si el usuario es nuevo, se crea el usuario y se lo envía a la configuración de crear hijos.
Si el usuario ya es usuario, se actualizan las wallets y se muestra el dashboard dinámico no hardcodeado.
Hacer Readme, técnico.
Hacer video Demo funcionando. 5’.
Funcionalidades que pensamos: Integración con Manteca. Ya sabemos como hacerlo, y poner los pasos del research que hicimos para esa integración de on-ramp y porque es importante hacerlo.
Fecha límite: 13/10/2024 11:00 am
En qué desafíos nos enfocamos.
Funcionalidades que desarrollamos.
Que diferencia hicimos en esta hackathon que en otras.
Tecnologías que usamos
Links a github
Video demo de 5’.




🏗 Piggy Wallet

Piggy Wallet is a decentralized application (dApp) designed to facilitate secure and automated cryptocurrency investments, specifically tailored for families, parents, and children. With a transparent and friendly interface, Piggy Investment allows users to easily manage their crypto investments through Dollar-Cost Averaging (DCA) strategies.


Features
Login with Privy: Securely log in using Privy and link your account with Safe to manage your assets.
Deploy a Base Testnet
Se implementó una base de datos para guardar datos de los usuarios, el mail y el address asociado. Si el usuario no se registra con mail, guardamos solo el address.
Si el usuario es nuevo, se crea el usuario y se lo envía a la configuración de crear hijos.







Piggy Wallet
Descripción del Proyecto
Piggy Wallet es una aplicación innovadora que utiliza tecnología blockchain para ayudar a las familias a ahorrar y educar financieramente a sus hijos en economías afectadas por la alta inflación. Nuestra plataforma ofrece una experiencia segura, intuitiva y accesible tanto para padres como para niños, permitiendo gestionar ahorros de manera efectiva y enseñar hábitos financieros saludables desde una edad temprana.
Desafíos Enfocados
Protección contra la inflación: Brindar una solución que permita a las familias proteger sus ahorros de la devaluación de la moneda local.
Educación financiera temprana: Facilitar el aprendizaje financiero de los niños de forma práctica y adaptada a su edad.
Accesibilidad tecnológica: Eliminar barreras técnicas asociadas con las criptomonedas y la tecnología blockchain, ofreciendo una interfaz sencilla y amigable.
Transacciones cross-chain: Implementar un sistema que permita operaciones en múltiples cadenas de bloques de manera eficiente y segura.
Persistencia y seguridad de datos: Integrar una base de datos robusta que garantice la integridad y disponibilidad de la información de los usuarios.
Funcionalidades Desarrolladas
1. Registro y Autenticación con Privy
Generación Automática de Wallets: Al registrarse con un correo electrónico, el usuario obtiene automáticamente una wallet generada por Privy, eliminando la complejidad de crear y gestionar wallets de criptomonedas.
Generación de Smart Accounts: Estas cuentas permiten que los usuarios manejen sus wallets a través de contratos inteligentes en lugar de tener que interactuar directamente con la blockchain. Las Smart Accounts facilitan automatizaciones y permisos avanzados, mejorando la experiencia del usuario. Privy nos permite la gestión y generación de estas smart accounts
Integración con Safe: Safe asegura que todas las transacciones dentro de la cuenta inteligente sigan una estructura segura y predefinida. Esto incluye la verificación de múltiples firmas para validar transacciones críticas, asegurando un mayor nivel de seguridad para las wallets generadas automáticamente por Privy.
Seguridad Mejorada: Al utilizar Privy, garantizamos que las credenciales de acceso y las claves privadas estén protegidas bajo estándares de seguridad de alto nivel.
Flujo de Usuario Personalizado:
Usuarios Nuevos: Si el usuario es nuevo, el sistema crea su perfil y lo redirige a la configuración para añadir información de sus hijos.
Usuarios Existentes: Si el usuario ya tiene una cuenta, se actualizan sus wallets y se muestra un dashboard dinámico con información actualizada.
2. Transacciones Cross-Chain con Soporte Multi-Chain
Implementación de Depósitos en Múltiples Cadenas: Hemos desarrollado métodos para realizar transacciones cross-chain, permitiendo a los usuarios depositar fondos desde diversas redes blockchain como Ethereum Sepolia, Optimism, Arbitrum, Polygon zkEVM, Avalanche Fuji y Base Sepolia.
Uso de USDC y CCTP de Circle: Utilizamos el USD Coin (USDC) y el protocolo Cross-Chain Transfer Protocol (CCTP) de Circle para facilitar transferencias de valor estables y confiables entre diferentes cadenas.
Código Personalizado para Gestión de Transacciones:
Componente Swapper: Desarrollamos un componente React que permite a los usuarios seleccionar la red de origen, ingresar el monto a transferir y gestionar el proceso completo de transferencia cross-chain.
Interacción con Contratos Inteligentes: El código interactúa con contratos inteligentes como TokenMessenger y MessageTransmitter para quemar tokens en la cadena de origen y mint tokens en la cadena de destino.
Gestión de Eventos y Logs: Implementamos lógica para extraer y procesar eventos de la blockchain, necesarios para validar y completar las transacciones.
Manejo de Errores y Cambio de Redes:
Cambio Automático de Redes en Metamask: El sistema solicita al usuario cambiar de red en Metamask según sea necesario para completar la transacción cross chain.
Gestión de Excepciones: Se implementaron mecanismos para manejar errores comunes, como la red no disponible en Metamask, ofreciendo soluciones alternativas como agregar la red automáticamente.
Prueba de transacciones en red de prueba de Base Sepolia: A continuación se dejan los links de algunos ejemplos de transacciones realizadas en el proceso de desarrollo para testear el uso de la red base en el depósito de tokens USDC en la smart account. Estas transacciones son depósitos de fondos realizados desde la app.
links: 
https://sepolia.basescan.org/tx/0x75aa511f71c16300c29d8a13b205e47e72fbf575c3ddc00b736bce0e729cdc8d
https://sepolia.basescan.org/tx/0xb03fad7fdb71b9383d8f0ae3b707ae4129192ca59327ecab371cbd5d51c3440e
3. Integración de Base de Datos Relacional con PostgreSQL y Sequelize
Migración desde Datos Hardcodeados: Anteriormente, la aplicación no contaba con persistencia de datos y utilizaba información estática. Implementamos una base de datos relacional para mejorar la escalabilidad y funcionalidad.
Modelos de Datos Normalizados:
Usuario (User): Almacena información básica como correo electrónico y dirección de wallet. Si el usuario no registra un correo, solo se guarda la dirección.
Hijo (Child): Modelo que representa a los hijos asociados a un usuario, permitiendo gestionar perfiles y objetivos de ahorro individuales.
Wallet de Usuario (UserWallet): Relaciona a los usuarios con sus diferentes wallets, permitiendo gestionar múltiples cuentas o activos.
KYC de Usuario (UserKYC): Preparado para integrar procesos de verificación de identidad cuando implementemos el on-ramp con Manteca.
Funciones de CRUD Mejoradas: Desarrollo de funciones para crear, leer, actualizar y eliminar registros en la base de datos, asegurando integridad y consistencia de la información.
4. Preparación para Integración con Manteca (On-Ramp)
Investigación y Planificación: Realizamos un análisis detallado sobre cómo integrar Manteca, un servicio que permite depósitos de fondos desde MercadoPago directamente a la blockchain. Nos reunimos con el fundador de Manteca quien nos explicó detalladamente el proceso para que nos conectemos a su plataforma.
Beneficios Identificados:
Facilitar la Adquisición de Criptomonedas: Permitir a los usuarios comprar criptomonedas utilizando métodos de pago locales y familiares.
Ampliar el Acceso al Servicio: Reducir las barreras de entrada para usuarios que no están familiarizados con exchanges o procesos complejos de compra.
Enlaces y Recursos:
Documentación de Manteca: Incluimos referencias y enlaces a la documentación oficial para facilitar futuras implementaciones.
5. Dashboard Dinámico y Personalizado
Visualización de Información en Tiempo Real:
Balances Actualizados: Mostrar el balance actual de las wallets del usuario, incluyendo conversiones a pesos argentinos para una comprensión más intuitiva.
Objetivos de Ahorro: Permitir la creación y seguimiento de objetivos financieros específicos para cada hijo.
Interfaz Intuitiva: Diseño de una UI amigable y fácil de navegar, adaptada tanto para adultos como para niños.
Experiencia de Usuario Mejorada: Implementación de funcionalidades que responden al comportamiento y necesidades del usuario, como notificaciones y recordatorios.
6. Funcionalidades Adicionales y Mejoras
Validación y Redirección en Inicio de Sesión:
Verificación de Existencia de Usuario: Al iniciar sesión, el sistema verifica si el usuario ya existe en la base de datos.
Redirección Inteligente: Los usuarios nuevos son redirigidos al proceso de configuración inicial (agregar hijos), mientras que los usuarios existentes acceden directamente al dashboard.
Lectura y Conversión de Balances:
Monitoreo de Fondos en Wallets: Implementamos funciones para leer el balance de fondos en las wallets de los usuarios.
Conversión a Moneda Local: Mostramos el equivalente en pesos argentinos, facilitando la comprensión del valor real de los ahorros.
7. Soporte y Escalabilidad
Arquitectura Modular: El código está estructurado de manera modular, facilitando la adición de nuevas funcionalidades y el mantenimiento.
Preparación para Escalamiento: La implementación de una base de datos relacional y el uso de ORM permiten una escalabilidad horizontal a medida que crece la base de usuarios.
Seguridad y Cumplimiento: Aunque no se ha implementado completamente, se planifica integrar procesos de KYC y cumplimiento normativo para garantizar la seguridad y confianza en el servicio.
Innovaciones en Esta Hackathon
Persistencia de Datos Mejorada: La integración de una base de datos relacional representó un avance significativo respecto a versiones anteriores, permitiendo una gestión de datos más robusta y eficiente.
Transacciones Cross-Chain Avanzadas: El soporte para múltiples cadenas y la implementación de transacciones cross-chain con CCTP de Circle es una innovación que amplía las posibilidades de uso y accesibilidad del servicio.
Enfoque en la Experiencia de Usuario: Se realizaron mejoras sustanciales en el flujo de usuario y en la interfaz, priorizando la usabilidad y simplificando procesos complejos.
Preparación para On-Ramp Local: La investigación y planificación para integrar Manteca demuestra nuestro compromiso por adaptarnos al contexto local y facilitar el acceso a la tecnología blockchain.
Tecnologías Utilizadas
Fullstack:
Next.js: Framework de React que permite renderizado del lado del servidor y generación de sitios estáticos.
React Hooks y Context API: Para gestión eficiente del estado y lógica compartida.
Sequelize ORM: Herramienta para interactuar con la base de datos PostgreSQL de manera eficiente y segura.
Base de Datos:
PostgreSQL: Sistema de gestión de bases de datos relacional de código abierto.
Blockchain y Criptomonedas:
Ethereum y Redes de Prueba: Uso de Ethereum Sepolia, Optimism, Arbitrum, Polygon zkEVM, Avalanche Fuji y Base Sepolia.
Ethers.js: Librería para interactuar con la blockchain de Ethereum.
USDC y CCTP de Circle: Para facilitar transacciones estables y cross-chain.
Autenticación y Seguridad:
Privy: Plataforma para gestión de identidades y wallets de manera segura.
Herramientas y Servicios Adicionales:
Manteca: Servicio planificado para integración de on-ramp desde MercadoPago.
Metamask: Extensión de navegador para interacción con wallets y redes blockchain.
API de Circle (Iris API): Utilizada para obtener atestaciones y validar transacciones cross-chain.
Enlaces Importantes
Repositorio GitHub: https://github.com/Rocking-Product/piggy-wallet
Demo en Vivo: https://piggy-wallet-demo.com
Documentación de Manteca: https://www.manteca.dev
Cómo Ejecutar el Proyecto
Clonar el repositorio:

git clone https://github.com/Rocking-Product/piggy-wallet.git	

Instalar las dependencias:
	
npm install
Configurar las variables de entorno:
Crear un archivo .env en la raíz del proyecto.
Añadir las variables necesarias siguiendo el formato del archivo .env.example.
Variables clave:
DATABASE_URL: URL de conexión a la base de datos PostgreSQL.
NEXT_PUBLIC_PRIVY_APP_ID: Clave de API de Privy.
CIRCLE_API_KEY: Clave de API de Circle para CCTP.
NEXT_PUBLIC_PIMLICO_API_KEY: Clave de API de PIMLICO.
Iniciar la aplicación en modo desarrollo:

npm run dev
Acceder a la aplicación:
Abrir un navegador web y navegar a http://localhost:3000.
Feedback Usuarios
Emilio tiene 42 años, tiene dos hijos de 9 y 6 años. Trabaja en tecnología y ha estado invirtiendo desde joven, aunque siempre ha sentido que le hubiera gustado recibir más formación financiera. Como muchos padres en Argentina, Emilio está preocupado por la constante inflación y busca maneras de enseñarles a sus hijos sobre el valor del dinero y cómo manejarlo desde pequeños. 

De la conversación con Emilio destacamos lo siguiente:
“Cuando eran más chicos, les daba dinero de vez en cuando, pero ahora quiero que entiendan que el dinero no aparece de la nada, sino que hay que ganarlo. Entonces ahora nos ayudan con tareas de la casa. Con la app, pueden ver que deben cumplir con tareas en la casa para recibir recompensas. Es una forma muy práctica de que aprendan que el esfuerzo tiene valor.”

“En una economía como la nuestra, donde la moneda pierde valor rápido, me parece fundamental que entiendan desde chicos que hay maneras de protegerlo y hacerlo rendir más. La app lo hace simple y visual, algo que me parece esencial. Sería ideal que sea como un juego, al estilo Duolingo, que hace que aprender un idioma sea más divertido. Me imagino algo así. Me parece muy atractivo y sería algo por lo que usaría la app, si les facilita a mis hijos el aprendizaje sobre el dinero, ahorro e inversiones.”

“Por lo que usaría la app, varias cosas. Principalmente para el aprendizaje, si puedo hacer que las tareas de la casa sean más entretenidas y tengan una motivación más para realizarlas al mismo tiempo que aprenden sobre el valor del dinero y el trabajo. Luego mostrarles que si eso no se lo gastan y lo ahorran, pueden comprar otras cosas que desean, y que adquieran el hábito del ahorro. Y si después les muestro que si eso lo invierten, pueden ver crecer su dinero. Ahí sí me imagino alguna animación que muestre los rendimientos de manera atractiva, como una plantita que crece y da frutos, o algo por ese estilo.”

“Lo que pienso que sería un gran plus es usarlo como billetera virtual también, poder darles dinero y controlar los gastos que hacen, les puedo dar autonomía para que ellos hagan y también se equivoquen. O que elijan invertirlo como hablamos. También si se incluyen cursos o guías para invertir, de forma didáctica o con videos animados”
