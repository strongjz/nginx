# nginx

<!---
Note: Do NOT edit directly, this file was generated using https://github.com/chainguard-images/readme-generator
-->

[![CI status](https://github.com/distroless/nginx/actions/workflows/release.yaml/badge.svg)](https://github.com/distroless/nginx/actions/workflows/release.yaml)

A minimal nginx base image rebuilt every night from source.

## Get It!

The image is available on `distroless.dev`:

```
docker pull distroless.dev/nginx:latest
```

## Supported tags

| Tag | Digest | Arch |
| --- | ------ | ---- |
| `latest` | `sha256:5a87591e4281db15ee14c2bd76bcfb62fb7befb9b9dcd1fffb3ea7bc115d0213`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:5a87591e4281db15ee14c2bd76bcfb62fb7befb9b9dcd1fffb3ea7bc115d0213) | `amd64` `arm64` `armv7` |
| `1` `1.23` `1.23.1` `1.23.1-r0` `mainline` | `sha256:c4b7701d82c4c58178a7c008dc7f08506552b546ffdd2f9ccf0b5f88d1154704`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:c4b7701d82c4c58178a7c008dc7f08506552b546ffdd2f9ccf0b5f88d1154704) | `amd64` `arm64` `armv7` |
| `1.22` `1.22.0` `1.22.0-r0` `stable` | `sha256:bc619cae72304858652b74a1e21d28badf64c439e5c19bf8647d20967c6a35bf`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:bc619cae72304858652b74a1e21d28badf64c439e5c19bf8647d20967c6a35bf) | `amd64` `arm64` `armv7` |


## Usage

To try out the image, run:

```
docker run -p 8080:80 cgr.dev/chainguard/nginx
```

If you navigate to `localhost:8080`, you should see the nginx welcome page.

To run an example Hello World app, navigate to the root of this repo and run:

```
docker run -v $(pwd)/examples/hello-world/site-content:/var/lib/nginx/html -p 8080:80 cgr.dev/chainguard/nginx
```

If you navigate to `localhost:8080`, you should see `Hello World from Nginx!`.



## Signing

All Chainguard Images are signed using [Sigstore](https://sigstore.dev)!

<details>
<br/>
To verify the image, download <a href="https://github.com/sigstore/cosign">cosign</a> and run:

```
COSIGN_EXPERIMENTAL=1 cosign verify distroless.dev/nginx:latest | jq
```

Output:
```
Verification for distroless.dev/nginx:latest --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - Existence of the claims in the transparency log was verified offline
  - Any certificates were verified against the Fulcio roots.
[
  {
    "critical": {
      "identity": {
        "docker-reference": "ghcr.io/distroless/nginx"
      },
      "image": {
        "docker-manifest-digest": "sha256:5a87591e4281db15ee14c2bd76bcfb62fb7befb9b9dcd1fffb3ea7bc115d0213"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "aac96edd74b39bb10f7bcfb445fa0f289a8df490",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "distroless/nginx",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEQCIEizoFo2oSAyyXUquTuvM4T6n04Qsbha1yJUn5s6NnkKAiBuoRFoK3hGCh+2qrEoXAmhPnewggvboBj/xnXFxXWSVw==",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiIyZjlhNzJlNDMxNjk0MjA3NTg2MjgxODcxNzg0MWI5NDZmMGQ2YTQ0ZWFmMDVjYjlhM2RiOTZkMTNmY2ZmMTU1In19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJQVR2QU9obmZPRVpXc1RYTXRnL3FHUk9maWZKODJ6bS84VG81dDF3NUxmWkFpRUEwSWRxM0RSeUluaE1UMWlEei9nQjdFa3hwNFp3cFNnOGtnbHVSeDFrQ1ZrPSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUnVSRU5EUVhsSFowRjNTVUpCWjBsVlRISkRiWGdyTmt0TGNtMDJjbkpWWTFWNlJuSmFlR0ZhWW1WQmQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEpkMDlVU1hkTlJFVXdUV3BWTTFkb1kwNU5ha2wzVDFSSmQwMUVSVEZOYWxVelYycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVYyTTNObldYRmFObUZwYjNGemFXOVZZVk50ZVhKNVpEQTBNRWhOY2trMWJVcFpVSE1LUzB4WVJ5dFFlSGxEUkZoS2NWRlhhMlJETmtKaVduSXJjVTVTVFZOSVNUTXhNWHB3UW5KQmNEUjBVRXd4T1M5d1NYRlBRMEZyUVhkblowazRUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZCY0dsYUNtbDFXVlZyTTNWWVFYVm9aRTFZYVRSalFVMU5kMDVqZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFsQldVUldVakJTUVZGSUwwSkdXWGRXU1ZwVFlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKU2NHTXpVbmxpTW5oc1l6Tk5kZ3BpYldSd1ltNW5ka3h0WkhCa1IyZ3hXV2s1TTJJelNuSmFiWGgyWkROTmRtTnRWbk5hVjBaNldsTTFOVmxYTVhOUlNFcHNXbTVOZG1GSFZtaGFTRTEyQ21KWFJuQmlha0UxUW1kdmNrSm5SVVZCV1U4dlRVRkZRa0pEZEc5a1NGSjNZM3B2ZGt3elVuWmhNbFoxVEcxR2FtUkhiSFppYmsxMVdqSnNNR0ZJVm1rS1pGaE9iR050VG5aaWJsSnNZbTVSZFZreU9YUk5RbGxIUTJselIwRlJVVUpuTnpoM1FWRkpSVU5JVG1waFIxWnJaRmQ0YkUxRVdVZERhWE5IUVZGUlFncG5OemgzUVZGTlJVdEhSbWhaZW1zeVdsZFNhMDU2VW1sTmVteHBXV3BGZDFwcVpHbFpNbHBwVGtSUk1WcHRSWGRhYWtrMFQxZEZORnBIV1RCUFZFRjNDa2hCV1V0TGQxbENRa0ZIUkhaNlFVSkNRVkZQVVROS2JGbFlVbXhKUmtwc1lrZFdhR015VlhkSVoxbExTM2RaUWtKQlIwUjJla0ZDUWxGUlVWcEhiSG9LWkVoS2RtSkhWbnBqZVRsMVdqSnNkV1ZFUVdSQ1oyOXlRbWRGUlVGWlR5OU5RVVZIUWtFNWVWcFhXbnBNTW1oc1dWZFNla3d5TVdoaFZ6UjNaMWx2UndwRGFYTkhRVkZSUWpGdWEwTkNRVWxGWmtGU05rRklaMEZrWjBGSldVcE1kMHRHVEM5aFJWaFNNRmR6Ym1oS2VFWmFlR2x6Um1velJFOU9TblExY25kcENrSnFXblpqWjBGQlFWbE9XV3RCVld4QlFVRkZRWGRDU0UxRlZVTkpTR1k0ZUVsa0wxVXlNVEJMYzJwMVpIbzROSGQ2UlRWcFUwOUxhWFZST1ZGT01tUUtZM2x2TmsxTEswVkJhVVZCYWpGWGVEQnFVRGsyVDJreWNHOVlTV1puZW1SelRVNXdjVlZRYVV4TGNtMUVTM2xGVEcxeVQyeEJNSGREWjFsSlMyOWFTUXA2YWpCRlFYZE5SR0ZSUVhkYVowbDRRVXhwTUdKcVlXVkdTV05WWVdGTGVXSXdkM1ZvTlZsUmJsSk5LelpOZDFKbGVFTXJiRGRVTVdaT2FESmhVMk51Q2tKeWRIZGFiRkJqWkRCV1ZXZG9ZMEpqZDBsNFFVeHVUSGhSWVM5Q1dWUkpiWGRyUVhwUlZsRTRWbFpzSzBJNGJrVXZRamxXTTB0cFpYbE5lbFEzY1VvS1luZ3JlbUZ1VmpBMGNXVlBhREp6UW1aU1ozTkpRVDA5Q2kwdExTMHRSVTVFSUVORlVsUkpSa2xEUVZSRkxTMHRMUzBLIn19fX0=",
          "integratedTime": 1663638193,
          "logIndex": 3575173,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/distroless/nginx/.github/workflows/release.yaml@refs/heads/main",
      "run_attempt": "1",
      "run_id": "3086762430",
      "sha": "aac96edd74b39bb10f7bcfb445fa0f289a8df490"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

