# Load Environment Variables From A File

__Category: Python__

Environment variables in a Python application can be loaded from a `.env` file using the `dotenv` package.

Add the package:

```shell
pip install python-dotenv
```

Assume you have a `.env` file in the root directory of your project:

```text
export DOMAIN="someserver.com" 
export SMTP_HOST="mail.${DOMAIN}" 
export BATCH_INTERVAL="2"
```

Load environment variables as follows:

```python
from dotenv import load_dotenv

# Load .env file
load_dotenv()

# Get values from .env file
smtp_host = os.getenv("SMTP_HOST")
batch interval = os.getenv("BATCH INTERVAL")
```

__Note:__ Add .env to your `.gitignore` file to ensure the file is not added to version control.

See [python-dotenv](https://pypi.org/project/python-dotenv) for more details.
