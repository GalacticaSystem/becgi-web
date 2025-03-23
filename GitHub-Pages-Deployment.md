# Estrategia de despliegue en GitHub Pages para BE-cGi Web

## Enfoque de despliegue

Hemos optado por utilizar el método tradicional de GitHub Pages para Jekyll en lugar de GitHub Actions:

1. **Método tradicional de GitHub Pages**:
   - GitHub Pages automáticamente construye y despliega sitios Jekyll
   - No requiere archivos de workflow personalizados
   - Es el mismo método utilizado en https://ronaldmego.github.io/

## Cambios realizados

Para implementar esta estrategia, hemos:

1. **Eliminado el workflow de GitHub Actions**:
   - El archivo `.github/workflows/jekyll-gh-pages.yml` ha sido respaldado
   - Ahora nos basamos en el proceso de construcción automática de GitHub Pages

2. **Asegurado la configuración correcta para Jekyll**:
   - Hemos actualizado el `Gemfile` para usar `github-pages`
   - Hemos respaldado el archivo `.nojekyll` que impediría el procesamiento Jekyll
   - Configurado correctamente el `baseurl` como "/becgi-web" en `_config.yml`

3. **Corregido inconsistencias de recursos**:
   - Corregidas las referencias a imágenes y recursos
   - Agregados marcadores de posición para recursos críticos

## Configuración en GitHub

Para que esto funcione, asegúrate de que en la configuración del repositorio:

1. Ve a `Settings` > `Pages`
2. En "Source", selecciona la rama `main` (o la rama que estés usando)
3. En "Build and deployment", elige "Deploy from a branch" (no "GitHub Actions")
4. Guarda la configuración

## Solución de problemas

Si el sitio sigue sin funcionar correctamente después de estos cambios:

1. Verifica en la configuración de GitHub Pages (Settings > Pages) que el sitio está configurado para construirse desde la rama correcta
2. Confirma que no hay errores de construcción en la sección "Pages build and deployment" de la pestaña de Actions
3. Asegúrate de que todas las rutas en los archivos HTML y Markdown usen `{{ site.baseurl }}` correctamente

## Recomendación para desarrollo local

Para probar el sitio localmente, utiliza:

```bash
bundle exec jekyll serve --baseurl=""
```

O simplemente ejecuta el archivo `run-local-server.bat` incluido.
