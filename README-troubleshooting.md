# Troubleshooting BE-cGi Website

## Problema: Error 404 en GitHub Pages

Actualmente estamos experimentando un error 404 al intentar acceder al sitio web de BE-cGi en GitHub Pages:
```
https://galacticasystem.github.io/becgi-web/
```

## Cambios realizados para solucionar el problema

Hemos identificado varios posibles problemas y realizado los siguientes cambios:

1. **Configuración de GitHub Actions**:
   - Creado el directorio `.github/workflows/`
   - Agregado el archivo `jekyll-gh-pages.yml` con la configuración adecuada para construir y desplegar el sitio

2. **Archivo .nojekyll**:
   - Eliminado el archivo `.nojekyll` que estaba evitando que GitHub Pages procesara el sitio con Jekyll

3. **Actualización del Gemfile**:
   - Actualizado el Gemfile para utilizar `github-pages` para mejor compatibilidad

4. **Corrección de inconsistencias en imágenes y rutas**:
   - Corregida referencia de `logo.png` a `logo.jpeg` en archivos de configuración
   - Agregadas imágenes de marcador de posición para evitar errores 404 en recursos críticos

5. **Verificación del CSS**:
   - Asegurado que el CSS respete los colores del PDF corporativo

## Pasos para verificar la solución

1. Después de hacer push de los cambios, verifica la acción de GitHub en:
   ```
   https://github.com/GalacticaSystem/becgi-web/actions
   ```

2. Si el flujo de trabajo se completa correctamente, el sitio debería estar disponible en:
   ```
   https://galacticasystem.github.io/becgi-web/
   ```

3. Si sigue habiendo problemas, verifica los siguientes aspectos:
   - Asegúrate de que la rama `main` esté configurada como fuente para GitHub Pages en la configuración del repositorio
   - Revisa los logs de la acción de GitHub para identificar posibles errores
   - Verifica que el repositorio tenga permisos adecuados para publicar en GitHub Pages

## Configuración de desarrollo local

Para probar el sitio localmente:

1. Clona el repositorio:
   ```
   git clone https://github.com/GalacticaSystem/becgi-web.git
   cd becgi-web
   ```

2. Instala las dependencias:
   ```
   bundle install
   ```

3. Ejecuta el servidor local:
   ```
   bundle exec jekyll serve --baseurl=""
   ```

4. Accede al sitio en:
   ```
   http://localhost:4000
   ```

También puedes utilizar el archivo `run-local-server.bat` que ya incluye el parámetro `--baseurl=""` para evitar problemas de rutas.
