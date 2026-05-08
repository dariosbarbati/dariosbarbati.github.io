<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DS</title>
    <style>
        /* Estilos Globales y Reset */
        :root {
            --primary-bg: #1a233b; /* Color azul marino oscuro del header */
            --secondary-bg: #f5f5f7; /* Color de fondo claro del cuerpo */
            --text-dark: #333333;
            --text-light: #ffffff;
            --font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; /* Tipografía limpia */
            --border-color: #e0e0e0;
            --vcard-width: 480px; /* Ancho fijo para un look de tarjeta en desktop */
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: var(--font-family);
            background-color: var(--secondary-bg);
            color: var(--text-dark);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        /* Contenedor Principal (vCard) */
        .vcard-container {
            background-color: var(--text-light);
            width: var(--vcard-width);
            border-radius: 20px;
            overflow: hidden; /* Para que el header curvo y el footer no se salgan */
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1); /* Sombra suave para efecto flotante */
            display: flex;
            flex-direction: column;
        }

        /* Sección del Header (Azul) */
        .vcard-header {
            background-color: var(--primary-bg);
            color: var(--text-light);
            padding: 40px 20px;
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .profile-photo {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid var(--text-light);
            margin-bottom: 20px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }

        .profile-name {
            font-size: 28px;
            font-weight: 700;
            margin-bottom: 5px;
        }

        .profile-title {
            font-size: 16px;
            opacity: 0.8;
            margin-bottom: 30px;
        }

        /* Sección de Botones de Acción (Iconos) */
        .action-buttons {
            display: flex;
            justify-content: space-around;
            width: 100%;
            max-width: 350px;
        }

        .action-btn {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-decoration: none;
            color: var(--text-light);
            width: 70px;
        }

        .icon-circle {
            width: 50px;
            height: 50px;
            background-color: var(--text-light);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 8px;
            transition: transform 0.2s ease;
        }

        .action-btn:hover .icon-circle {
            transform: scale(1.1);
        }

        .icon-circle img {
            width: 24px;
            height: 24px;
            /* Invertimos el color de los iconos negros de ejemplo */
            filter: invert(1);
        }

        .action-label {
            font-size: 12px;
            font-weight: 500;
            text-transform: capitalize;
        }

        /* Sección del Cuerpo (Detalles de Contacto) */
        .vcard-body {
            padding: 30px 20px;
            flex-grow: 1; /* El cuerpo ocupa el espacio restante */
        }

        .contact-group {
            margin-bottom: 25px;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 15px;
        }

        .contact-group:last-child {
            border-bottom: none;
            margin-bottom: 0;
        }

        .contact-label {
            font-size: 12px;
            font-weight: 600;
            color: #888;
            margin-bottom: 5px;
            display: block;
        }

        .contact-value {
            font-size: 16px;
            color: var(--text-dark);
            text-decoration: none;
            display: block;
        }

        .contact-value:hover {
            color: #007bff; /* Color de enlace para hover */
        }

        .address-value {
            line-height: 1.5;
            white-space: pre-line; /* Mantiene saltos de línea del texto */
        }

        /* Botón de Acción Principal (Footer) */
        .vcard-footer {
            padding: 20px;
            text-align: center;
        }

        .add-contact-btn {
            display: inline-block;
            background-color: var(--primary-bg);
            color: var(--text-light);
            text-decoration: none;
            padding: 15px 40px;
            border-radius: 30px;
            font-weight: 700;
            font-size: 16px;
            transition: background-color 0.2s ease, transform 0.2s ease;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }

        .add-contact-btn:hover {
            background-color: #2c3e66;
            transform: translateY(-2px);
        }

        /* Media Query para Pantallas Pequeñas (Opcional, pero buena práctica) */
        @media (max-width: 500px) {
            :root {
                --vcard-width: 90%; /* Se ajusta a pantallas de teléfono */
            }
        }
    </style>
</head>
<body>

    <!-- Contenedor principal de la vCard -->
    <div class="vcard-container">

        <!-- CABECERA DE LA VCARD -->
        <header class="vcard-header">
            <!-- Reemplaza la URL de la imagen por tu foto de perfil real -->
            <img src="https://images.unsplash.com/photo-1599566150163-29194dcaad36?q=80&w=300&auto=format&fit=crop" alt="Foto de perfil de [Tu Nombre]" class="profile-photo">
           
            <h1 class="profile-name">Tu Nombre Aquí</h1>
            <p class="profile-title">Tu Título Profesional (ej. Desarrollador Web Senior)</p>

            <!-- Botones de Acción Instantánea -->
            <div class="action-buttons">
                <!-- Reemplaza con tu número de teléfono real -->
                <a href="tel:+525512345678" class="action-btn">
                    <div class="icon-circle">
                        <!-- Icono de teléfono -->
                        <img src="https://cdn-icons-png.flaticon.com/512/126/126509.png" alt="Icono Llamar">
                    </div>
                    <span class="action-label">Llamar</span>
                </a>
               
                <!-- Reemplaza con tu enlace de mensajería (ej. WhatsApp) -->
                <a href="https://wa.me/525512345678" class="action-btn">
                    <div class="icon-circle">
                        <!-- Icono de mensaje -->
                        <img src="https://cdn-icons-png.flaticon.com/512/2190/2190533.png" alt="Icono Mensaje">
                    </div>
                    <span class="action-label">Mensaje</span>
                </a>
               
                <!-- Reemplaza con tu correo real -->
                <a href="mailto:tuemail@ejemplo.com" class="action-btn">
                    <div class="icon-circle">
                        <!-- Icono de email -->
                        <img src="https://cdn-icons-png.flaticon.com/512/561/561127.png" alt="Icono Email">
                    </div>
                    <span class="action-label">Email</span>
                </a>
               
                <!-- Reemplaza con tu sitio web o perfil de LinkedIn real -->
                <a href="https://tupaginaweb.com" target="_blank" rel="noopener" class="action-btn">
                    <div class="icon-circle">
                        <!-- Icono de web -->
                        <img src="https://cdn-icons-png.flaticon.com/512/1006/1006771.png" alt="Icono Web">
                    </div>
                    <span class="action-label">Web</span>
                </a>
            </div>
        </header>

        <!-- CUERPO DE LA VCARD -->
        <main class="vcard-body">
            <!-- Grupo de Contacto: Teléfono -->
            <div class="contact-group">
                <span class="contact-label">Contacto (trabajo)</span>
                <!-- Reemplaza el texto y el enlace -->
                <a href="tel:+525512345678" class="contact-value">+52 55 1234 5678</a>
            </div>

            <!-- Grupo de Contacto: Correo -->
            <div class="contact-group">
                <span class="contact-label">Email</span>
                <!-- Reemplaza el texto y el enlace -->
                <a href="mailto:tuemail@ejemplo.com" class="contact-value">tuemail@ejemplo.com</a>
            </div>

            <!-- Grupo de Contacto: Dirección -->
            <div class="contact-group">
                <span class="contact-label">Dirección</span>
                <!-- Reemplaza con tu dirección real -->
                <p class="contact-value address-value">Tu Calle, Número,
                Ciudad, Estado, C.P.
                País</p>
            </div>
        </main>

        <!-- FOOTER DE LA VCARD -->
        <footer class="vcard-footer">
            <!-- Reemplaza este enlace por el enlace a tu archivo .vcf real si tienes uno -->
            <a href="#" class="add-contact-btn">Añadir a Contactos</a>
        </footer>

    </div>

</body>
</html>
