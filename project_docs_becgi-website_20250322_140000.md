# Documentación del proyecto BE-cGi Website

## Estado actual del proyecto
Fecha de actualización: 22 de marzo de 2025

### Estructura del proyecto
El proyecto actual es un sitio web basado en Jekyll para la empresa BE-cGi. Está configurado siguiendo una estructura estándar de Jekyll con las siguientes carpetas y archivos principales:

- **\_layouts/**: Contiene las plantillas para las páginas del sitio
- **\_posts/**: Contendrá las entradas del blog
- **\_projects/**: Contendrá los proyectos del portafolio
- **assets/**: Almacena recursos como CSS, imágenes y documentos
  - **css/**: Archivos de estilo, incluyendo style.scss
  - **docs/**: Documentos como PDFs
  - **images/**: Imágenes del sitio
- **Archivos principales**:
  - **index.md**: Página principal
  - **blog.md**: Página de blog
  - **portfolio.md**: Página de portafolio
  - **contact.md**: Página de contacto
  - **team.md**: Página del equipo
  - **\_config.yml**: Configuración del sitio Jekyll

### Cambios realizados
1. Se corrigió un error en el archivo `assets/css/style.scss` que impedía la compilación del sitio.
   - Se reemplazaron todas las instancias de `color.adjust()` por la función `darken()` que es compatible con la versión actual de Sass que usa Jekyll.
   - Se eliminó la importación `@use "sass:color";` que no era compatible.

### Paleta de colores
Basados en el PDF de presentación de BE-cGi, se han implementado los siguientes colores principales:

```scss
$primary-color: #26486e;  /* Azul oscuro, del fondo del PDF */
$primary-light: #3a6ba3;  /* Versión más clara del azul */
$secondary-color: #83244c;  /* Rojo borgoña, del segundo slide */
```

## Próximos pasos

### 1. Configuración de la marca
- [ ] Agregar el logotipo de BE-cGi en la carpeta `assets/images/`
- [ ] Actualizar la navegación para incluir el logotipo
- [ ] Revisar y ajustar la paleta de colores si es necesario para que coincida exactamente con la identidad visual de BE-cGi

### 2. Contenido de la página principal
- [ ] Crear una sección hero con el mensaje principal de BE-cGi: "A través del capital relacional aumentamos el capital económico de las organizaciones"
- [ ] Implementar una sección que explique la misión y visión de la empresa
- [ ] Desarrollar secciones para servicios principales
- [ ] Añadir sección de "Grandes organizaciones en América" para destacar clientes importantes

### 3. Desarrollo de la página de equipo
- [ ] Crear una estructura para la presentación del equipo
- [ ] Incluir secciones para describir los valores y principios de la empresa: Asertividad, transparencia, coherencia, etc.

### 4. Integración de stakeholders
Según el PDF, BE-cGi considera importantes a diferentes grupos de stakeholders. Se deben crear secciones para mostrar cómo la empresa se relaciona con:
- [ ] **Externos**: Clientes, Proveedores, Inversores, Gobiernos, etc.
- [ ] **Internos**: Empleados, Familias de empleados, etc.

### 5. Optimización técnica
- [ ] Implementar compresión de imágenes para mejorar el rendimiento
- [ ] Configurar metadatos SEO en \_config.yml
- [ ] Asegurar que el sitio sea responsivo para dispositivos móviles
- [ ] Probar la velocidad del sitio con herramientas como Lighthouse

### 6. Implementación de GitHub Pages
- [ ] Configurar correctamente GitHub Pages en el repositorio
- [ ] Asegurar que el dominio personalizado (si se va a usar) esté configurado correctamente
- [ ] Verificar que el sitio se despliegue correctamente con cada push al repositorio

## Solución de problemas comunes

### Error de SCSS/SASS
Si encuentras errores relacionados con Sass al compilar el sitio, verifica:
1. La sintaxis de tus archivos .scss
2. Asegúrate de que las funciones que uses sean compatibles con la versión de Sass que usa Jekyll (actualmente 3.7.4)
3. Si necesitas funciones más avanzadas, considera actualizar la versión de Jekyll y sass-converter

### Problemas de despliegue en GitHub Pages
1. Verifica que la rama correcta esté configurada en los ajustes de GitHub Pages
2. Asegúrate de que no haya errores de compilación revisando los logs de Actions
3. Comprueba que los archivos necesarios (como _config.yml) estén presentes y correctos

## Referencias
- [Documentación oficial de Jekyll](https://jekyllrb.com/docs/)
- [GitHub Pages](https://pages.github.com/)
- [Sass Documentation](https://sass-lang.com/documentation)
