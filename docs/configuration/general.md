# Allgemeine Einstellungen

Einige allgemeine Einstellungen sollten in ihrer `config/settings/local.py` enthalten sein. Die erste und wahrscheinlich wichtigste Einstellung ist, ob Sie RDMO im [Debug-Modus](https://docs.djangoproject.com/en/1.10/ref/settings/#std:setting-DEBUG) ausführen:

```python
DEBUG = True
```

Im Debug-Modus werden ausführliche Fehlerseiten angezeigt, falls etwas schief läuft, werden statische Inhalte wie CSS und JavaScript-Dateien vom Entwicklungsserver automatisch gefunden. Der Debug-Modus *darf nicht* aktiviert sein, wenn RDMO im normalen Betrieb mit dem Internet verbunden ist.

Django braucht einen [Geheimschlüssel](https://docs.djangoproject.com/en/1.10/ref/settings/#std:setting-SECRET_KEY), der auf einen einzigartigen, unvorhersehbaren Wert gesetzt wird:

```python
SECRET_KEY = 'this is not a very secret key'
```

Dieser Schlüssel muss geheim bleiben, da ansonsten viele der eingebauten Sicherheitsmaßnahmen von Django versagen.

Im Betrieb erlaubt Django nur [Anfragen an bestimmte URLs](https://docs.djangoproject.com/en/1.10/ref/settings/#allowed-hosts), welche festgelegt werden müssen:

```python
ALLOWED_HOSTS = ['localhost', 'rdmo.example.com']
```

Wenn Sie RDMO unter einem Alias wie http://example.com/rdmo laufen lassen möchten, müssen Sie die Basis-URL festlegen:

```python
BASE_URL = '/rdmo'
```

Ferner, möchten Sie vielleicht eine Hauptsprache für ihr RDMO und die Zeitzone festlegen:

```python
LANGUAGE_CODE = 'en-us'
TIME_ZONE = 'Europe/Berlin'
```
