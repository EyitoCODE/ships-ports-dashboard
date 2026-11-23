# Ships and ports in Canada

A public Python dashboard for exploring Canadian port and marina references and
experimental ship predictions from Sentinel-2 imagery.

- Open a saved Halifax or Vancouver example immediately.
- Filter 1,396 published facility references.
- Inspect predictions and download PNG, CSV, GeoJSON, and metadata.
- Ask the OpenRouter-powered assistant about the displayed result, select an
  example through chat, or filter the reference layer.
- Run the existing vessel detector on a small area when the host has configured
  Earth Engine access.

## Deployment

Deploy `code/app.py` on Streamlit Community Cloud with Python 3.13.
Python dependencies are in `code/requirements.txt`.

The host sets `OPENROUTER_API_KEY` in the app's private secret settings.
Chat requests use `openrouter/free`, with the provider's free usage limits.
For unattended live imagery, also configure `EE_PROJECT` and
`EE_SERVICE_ACCOUNT_JSON`. Visitors use the application without their own
service accounts or API keys.

The original preserved detector checkpoint downloads on the first live request
and is verified against its SHA-256. Saved demonstrations open independently of
the live imagery and chat services.

## Provenance

The [course project](https://github.com/AdityaR28/OSS4008A---Introduction-to-Remote-Sensing-and-Applications/tree/main/students/oritse-tsegbemi_eyito)
contains the Colab notebooks, training and evaluation history, data provenance,
and weekly progress log. This repository contains the visitor application's
deployment files.

Facility records use Statistics Canada ODI v2 and a separately attributed Yukon
park dock reference under the applicable government open licences.
The detector's original training data are the
[SEN2MS Vessel Bounding Boxes dataset](https://doi.org/10.5281/zenodo.15571607).
Predictions remain experimental and require independent Canadian validation.
