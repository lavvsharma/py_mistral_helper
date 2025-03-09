# Python Mistral Helper (Unofficial)

<p align="center">
<a href="https://pypi.org/project/py-mistral-helper" target="_blank">
    <img src="https://img.shields.io/pypi/v/py-mistral-helper?color=%2334D058&label=pypi%20package" alt="Package version">
</a>

<a href="https://pypistats.org/packages/py-mistral-helper" target="_blank">
    <img src="https://img.shields.io/pypi/dm/py-mistral-helper" alt="Downloads">
</a>
</p> 

MistralHelper simplifies text extraction from PDFs and images using Mistral-AI’s OCR models. It supports processing via
URLs or file uploads and ensures API key validation. The package encodes images, uploads documents, and retrieves
extracted text efficiently.

## Installation

```sh
# install from PyPI
pip install py_mistral_helper
```

## Generate API Key

Follow the official documentation of [Mistral](https://docs.mistral.ai/getting-started/quickstart/) to generate the API
Key.

## Usage

1. [Extract text using pdf document url](#extract-text-using-pdf-document-url)
2. [Extract text using pdf](#extract-text-using-pdf)
3. [Extract text using image url](#extract-text-using-image-url)
4. [Extract text using image](#extract-text-using-image)

## Initialize Client

```python
import os
from py_mistral_helper.MistralHelper import MistralHelper

client = MistralHelper(
    api_key=os.environ.get("MISTRAL_API_KEY"),
)
```

### Extract text using pdf document url

```python
import os
from py_mistral_helper.MistralHelper import MistralHelper

client = MistralHelper(
    api_key=os.environ.get("MISTRAL_API_KEY"),
)

extracted_text = client.extract_text_using_pdf_document_url("https://arxiv.org/pdf/2201.04234")
```

### Extract text using pdf

```python
import os
from py_mistral_helper.MistralHelper import MistralHelper

client = MistralHelper(
    api_key=os.environ.get("MISTRAL_API_KEY"),
)

extracted_text = client.extract_text_using_pdf("sample.pdf")
```

### Extract text using image url

```python
import os
from py_mistral_helper.MistralHelper import MistralHelper

client = MistralHelper(
    api_key=os.environ.get("MISTRAL_API_KEY"),
)

extracted_text = client.extract_text_using_image_url("https://www.mattmahoney.net/ocr/plaid_c150.jpg")
```

### Extract text using image

```python
import os
from py_mistral_helper.MistralHelper import MistralHelper

client = MistralHelper(
    api_key=os.environ.get("MISTRAL_API_KEY"),
)

extracted_text = client.extract_text_using_image_path("sample.jpg")
```

While you can provide an `api_key` keyword argument,
we recommend using [python-dotenv](https://pypi.org/project/python-dotenv/)
to add `MISTRAL_API_KEY="My API Key"` to your `.env` file
so that your API Key is not stored in source control.

## Versioning

This package generally follows [SemVer](https://semver.org/spec/v2.0.0.html) conventions, though certain
backwards-incompatible changes may be released as minor versions:

1. Changes that only affect static types, without breaking runtime behavior.
2. Changes to library internals which are technically public but not intended or documented for external use. _(Please
   open a GitHub issue to let us know if you are relying on such internals)_.
3. Changes that we do not expect to impact the vast majority of users in practice.

We take backwards-compatibility seriously and work hard to ensure you can rely on a smooth upgrade experience.

We are keen for your feedback; please open an [issue](https://github.com/lavvsharma/py_mistral_helper/issues) with
questions, bugs, or suggestions.

## Requirements

Python 3.12 or higher.
