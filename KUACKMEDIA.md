# Fork de kuackmedia

Fork de [BradyNadeau/cordova-plugin-native-settings](https://github.com/BradyNadeau/cordova-plugin-native-settings) en la versión `1.0.0` publicada en npm (MIT, ver `LICENSE`). Lo usan las apps Cordova de
Kuack Media para abrir los ajustes de Bluetooth del sistema desde el menú de Cast (`chromecast/ChromecastSession.js`).

Base: `515e482` (upstream no tiene tag de esa versión), idéntico al paquete `cordova-plugin-native-settings@1.0.0` de npm que las apps instalaban hasta noviembre de 2026.

El paquete de npm no salió de ningún commit tal cual: tiene finales de línea CRLF, otro README y un `.npmignore`. El código es el de `515e482` salvo los finales de línea. El commit siguiente trae el contenido exacto del paquete, así el build es idéntico al de `cordova-plugin-native-settings@1.0.0` de npm.

**Lo publicado es el commit fijado en `_common/configTemplates/config-app*.xml`** del repo de las apps
(`github:kuackmedia-apps/cordova-plugin-native-settings#<sha>`), no la punta de una branch: un push a este repo no llega a ningún
binario hasta que se mueve ese pin, y mover el pin es un diff que se revisa. La branch `kuack` es la línea de
Kuack; `master` queda como el de upstream.

## Cambios respecto de upstream

Ninguno en el código: el fork existe para que el app dependa sólo de Apache Cordova y de repos de Kuack (fila A18 del RFP de Claro, CM-RFP-001).

## Para actualizar desde upstream

`git fetch upstream --tags`, en una branch merge (o rebase) de la versión nueva sobre `kuack`, revisar los
cambios de arriba, probarlo en un app con `config-app-local.xml` (path local del checkout), llevarlo a `kuack` y
mover el pin en los `config-app*.xml`. Nunca cambiar el `id` del plugin ni sus `clobbers`: el bundle remoto lo
comparten los binarios publicados.
