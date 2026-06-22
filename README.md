# Kubernetes Per Comuni Mortali — landing page

Sito statico (HTML + CSS, nessuna build) del corso **Kubernetes Per Comuni Mortali**.

Viene servito da un'immagine `nginx` di base: nell'esempio sugli **initContainer**
del corso, un initContainer fa il `git clone` di questo repo in un volume `emptyDir`
e nginx serve i file, senza dover costruire un'immagine custom.

## Struttura

```
index.html        # pagina principale
css/style.css     # stili
img/logo.svg      # logo (ruota del timoniere)
img/favicon.svg   # favicon
```

## Anteprima in locale

```sh
# con Python
python3 -m http.server 8080
# poi apri http://localhost:8080

# oppure con nginx in un container
docker run --rm -p 8080:80 -v "$PWD":/usr/share/nginx/html:ro nginx:1.27-alpine
```
