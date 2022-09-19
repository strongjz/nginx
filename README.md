# nginx

<!---
Note: Do NOT edit directly, this file was generated using https://github.com/distroless/readme-generator
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
| `1` `1.23` `1.23.1` `1.23.1-r0` `latest` `mainline` | `sha256:8cc0d6283014f240b1d2f1663f5061aadf44f99f5e4b206cf61bee75ba37d16a`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:8cc0d6283014f240b1d2f1663f5061aadf44f99f5e4b206cf61bee75ba37d16a) | `amd64` `arm64` `armv7` |
| `1.22` `1.22.0` `1.22.0-r0` `stable` | `sha256:9b0463bbe159e0ef9ec0e848d757d7e0a8b4d0c90a3056b9a6e2053409b863e9`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:9b0463bbe159e0ef9ec0e848d757d7e0a8b4d0c90a3056b9a6e2053409b863e9) | `amd64` `arm64` `armv7` |


## Usage

To try out the image, run:

```
docker run -p 8080:80 distroless.dev/nginx
```

If you navigate to `localhost:8080`, you should see the nginx welcome page.

To run an example Hello World app, navigate to the root of this repo and run:

```
docker run -v $(pwd)/examples/hello-world/site-content:/var/lib/nginx/html -p 8080:80 distroless.dev/nginx
```

If you navigate to `localhost:8080`, you should see `Hello World from Nginx Distroless!`.



## Signing

All distroless images are signed using [Sigstore](https://sigstore.dev)!

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
        "docker-manifest-digest": "sha256:8cc0d6283014f240b1d2f1663f5061aadf44f99f5e4b206cf61bee75ba37d16a"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "8235c72b2f289b3a4652c359d18274f00588bd70",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "distroless/nginx",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEUCIQCvryZ6JktSjiEBZ4uZNoQYCGDXfQxLIEJ89b3MSm3gtgIgcAKsCiRJpGqYIa4Cl0SNuLgaMBIJ+LQy6pDc5fLS1dA=",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiIzMzg2MzQ3MTBiN2ExMzIyOWZkMmNjNjRjMWI2ODEyZGEwYzEwOWFiMWViNjEwODU3ZTc2ZjIxNGRmNWUzYjIwIn19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FUUNJQVBLOXVtSVc1U29iaVFuMlhoTThFWWRlMTA2bFdjUVcyanJpZXhSQ1ZUakFpQnVrSmVhMWFhb0FVZktscHMvdnkvUmgwQlFOQXNUb1JQaGw2ZjBYdGhlQUE9PSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUnRla05EUVhsTFowRjNTVUpCWjBsVlZ5dHhWWGszUTBsdWNuQmpUMjVpTW5OUlRWaGFkbTVDWlRFd2QwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEpkMDlVUlRSTlJFVjZUMVJOTkZkb1kwNU5ha2wzVDFSRk5FMUVSVEJQVkUwMFYycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVZLYVhKT2FtdDRUbE5JWmtwVlJtMVJXRmhCVUdaUWJEVnBNRzFyU0V0ck9YWXJWbFVLUjJ0Wk1rWkRhbU5YWWtOTWNuTjZXbXBWTUVkb2NHSTNObFpTVFd0T2NqTlpNbE0wUmpaR05UWlFVbmhQYld4dkwzRlBRMEZyUlhkblowazVUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZLTlcxVUNtNTNURXRtUWpneFVucDFWa0p0Wm5GeldqZDZSWGRSZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFsQldVUldVakJTUVZGSUwwSkdXWGRXU1ZwVFlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKU2NHTXpVbmxpTW5oc1l6Tk5kZ3BpYldSd1ltNW5ka3h0WkhCa1IyZ3hXV2s1TTJJelNuSmFiWGgyWkROTmRtTnRWbk5hVjBaNldsTTFOVmxYTVhOUlNFcHNXbTVOZG1GSFZtaGFTRTEyQ21KWFJuQmlha0UxUW1kdmNrSm5SVVZCV1U4dlRVRkZRa0pEZEc5a1NGSjNZM3B2ZGt3elVuWmhNbFoxVEcxR2FtUkhiSFppYmsxMVdqSnNNR0ZJVm1rS1pGaE9iR050VG5aaWJsSnNZbTVSZFZreU9YUk5RbGxIUTJselIwRlJVVUpuTnpoM1FWRkpSVU5JVG1waFIxWnJaRmQ0YkUxRVdVZERhWE5IUVZGUlFncG5OemgzUVZGTlJVdEVaM2xOZWxacVRucEthVTF0V1hsUFJHeHBUVEpGTUU1cVZYbFplazB4VDFkUmVFOUVTVE5PUjFsM1RVUlZORTlIU210T2VrRjNDa2hCV1V0TGQxbENRa0ZIUkhaNlFVSkNRVkZQVVROS2JGbFlVbXhKUmtwc1lrZFdhR015VlhkSVoxbExTM2RaUWtKQlIwUjJla0ZDUWxGUlVWcEhiSG9LWkVoS2RtSkhWbnBqZVRsMVdqSnNkV1ZFUVdSQ1oyOXlRbWRGUlVGWlR5OU5RVVZIUWtFNWVWcFhXbnBNTW1oc1dWZFNla3d5TVdoaFZ6UjNaMWx6UndwRGFYTkhRVkZSUWpGdWEwTkNRVWxGWmxGU04wRklhMEZrZDBGSldVcE1kMHRHVEM5aFJWaFNNRmR6Ym1oS2VFWmFlR2x6Um1velJFOU9TblExY25kcENrSnFXblpqWjBGQlFWbE9UMUZGV0ZGQlFVRkZRWGRDU1UxRldVTkpVVU5HUlhFd1FUTTFSREJTYVZBM2JEVk9VVWROVjJwQ1QxaHlhbFpEY2k5YWNFVUtMMUJxVFZKcllrMHpkMGxvUVU5M1RXeHFUbXhJV21vMFZVZFlUV053Y2tZM1dUQjBiR2wyTVVwbFYzbE5ZVUp1T0RSVmJVaFNWSGhOUVc5SFEwTnhSd3BUVFRRNVFrRk5SRUV5WTBGTlIxRkRUVVJMTTJveFJqWjJVbVZhVVVKS2FWTkRkR3N3VmsxUGFFd3ZkaTlxUVZVM1ZuWjZVbVJCZERWVlQwaFlVRUZ0Q25GWlozZEJkRzUzVUc1SWVVMUVUamR6WjBsM1dYYzBkbUpDVTFkbU1ITnFNM29yVTNoNmJFTnZkbU5zYmsxb2NrMU1iVWN4WkRSclpGQmpjR0ZGVkZBS1JrWjRkbE5TUWtnME1FaERNbmxVUTJVMWEza0tMUzB0TFMxRlRrUWdRMFZTVkVsR1NVTkJWRVV0TFMwdExRbz0ifX19fQ==",
          "integratedTime": 1663465186,
          "logIndex": 3527857,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/distroless/nginx/.github/workflows/release.yaml@refs/heads/main",
      "run_attempt": "1",
      "run_id": "3075438701",
      "sha": "8235c72b2f289b3a4652c359d18274f00588bd70"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [melange](https://github.com/chainguard-dev/melange) and [apko](https://github.com/chainguard-dev/apko).

