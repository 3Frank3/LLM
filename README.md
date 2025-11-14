# LLM

## Setup

1. (Recommended) Create and activate a virtual environment.
2. Install the workshop dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Torch security note

The Hugging Face models that are loaded throughout the notebooks rely on `torch.load`.  
PyTorch versions older than 2.6.0 can no longer execute `torch.load` because of
[CVE-2025-32434](https://nvd.nist.gov/vuln/detail/CVE-2025-32434).
If you see an error similar to:

```
ValueError: Due to a serious vulnerability issue in torch.load ... we now require users to upgrade torch to at least v2.6
```

make sure you re-install PyTorch at version 2.6.0 or newer (for Apple Silicon,
use the wheel from https://download.pytorch.org/whl/cpu). The dependencies in
`requirements.txt` already pin the minimum safe version, so `pip install -r requirements.txt`
is the easiest way to upgrade.
