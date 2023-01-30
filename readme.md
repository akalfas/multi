use acr for multi-arch
======================

take #1
=======

```bash

$ az acr run -g ak-estargz -r estargz -f all.yaml .
Packing source code into tar to upload...
Excluding '.gitignore' based on default ignore rules
Excluding '.git' based on default ignore rules
Uploading archived source code from '/var/folders/c_/dqhl6r4n179dqqmk_9chgkz00000gn/T/cli_source_archive_b230975355b64795abad4bacff787619.tar.gz'...
Sending context (4.723 KiB) to registry: estargz...
Queued a run with ID: cb1q
Waiting for an agent...
2023/01/30 11:30:24 Downloading source code...
2023/01/30 11:30:25 Finished downloading source code
2023/01/30 11:30:25 Alias support enabled for version >= 1.1.0, please see https://aka.ms/acr/tasks/task-aliases for more information.
2023/01/30 11:30:25 Creating Docker network: acb_default_network, driver: 'bridge'
2023/01/30 11:30:25 Successfully set up Docker network: acb_default_network
2023/01/30 11:30:25 Setting up Docker configuration...
2023/01/30 11:30:26 Successfully set up Docker configuration
2023/01/30 11:30:26 Logging in to registry: estargz.azurecr.io
2023/01/30 11:30:26 Successfully logged into estargz.azurecr.io
2023/01/30 11:30:26 Executing step ID: acb_step_0. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:30:26 Scanning for dependencies...
2023/01/30 11:30:27 Successfully scanned dependencies
2023/01/30 11:30:27 Launching container with name: acb_step_0
Sending build context to Docker daemon  43.01kB
Step 1/2 : FROM ubuntu
latest: Pulling from library/ubuntu
10175de2f0c4: Pulling fs layer
10175de2f0c4: Verifying Checksum
10175de2f0c4: Download complete
10175de2f0c4: Pull complete
Digest: sha256:27cb6e6ccef575a4698b66f5de06c7ecd61589132d5a91d098f7f3f9285415a9
Status: Downloaded newer image for ubuntu:latest
 ---> 4c2c87c6c36e
Step 2/2 : CMD ["uname", "-a"]
 ---> [Warning] The requested image's platform (linux/arm64/v8) does not match the detected host platform (linux/amd64) and no specific platform was requested
 ---> Running in e836c3719750
Removing intermediate container e836c3719750
 ---> a990a1d7e239
Successfully built a990a1d7e239
Successfully tagged estargz.azurecr.io/multi-multi/aem:arm
2023/01/30 11:30:37 Successfully executed container: acb_step_0
2023/01/30 11:30:37 Executing step ID: acb_step_1. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:30:37 Pushing image: estargz.azurecr.io/multi-multi/aem:arm, attempt 1
The push refers to repository [estargz.azurecr.io/multi-multi/aem]
80ac6c107b7b: Preparing
80ac6c107b7b: Layer already exists
arm: digest: sha256:47dbf6652bc30ab4793046993624be9957246ca7e13283f6ec6abee297f6776f size: 529
2023/01/30 11:30:38 Successfully pushed image: estargz.azurecr.io/multi-multi/aem:arm
2023/01/30 11:30:38 Executing step ID: acb_step_2. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:30:38 Scanning for dependencies...
2023/01/30 11:30:39 Successfully scanned dependencies
2023/01/30 11:30:39 Launching container with name: acb_step_2
Sending build context to Docker daemon  43.01kB
Step 1/2 : FROM ubuntu
 ---> 4c2c87c6c36e
Step 2/2 : CMD ["uname", "-a"]
 ---> Using cache
 ---> a990a1d7e239
Successfully built a990a1d7e239
Successfully tagged estargz.azurecr.io/multi-multi/aem:x64
2023/01/30 11:30:40 Successfully executed container: acb_step_2
2023/01/30 11:30:40 Executing step ID: acb_step_3. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:30:40 Pushing image: estargz.azurecr.io/multi-multi/aem:x64, attempt 1
The push refers to repository [estargz.azurecr.io/multi-multi/aem]
80ac6c107b7b: Preparing
80ac6c107b7b: Layer already exists
x64: digest: sha256:47dbf6652bc30ab4793046993624be9957246ca7e13283f6ec6abee297f6776f size: 529
2023/01/30 11:30:41 Successfully pushed image: estargz.azurecr.io/multi-multi/aem:x64
2023/01/30 11:30:41 Executing step ID: acb_step_4. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:30:41 Launching container with name: acb_step_4
Created manifest list estargz.azurecr.io/multi-multi/aem:multi
2023/01/30 11:30:42 Successfully executed container: acb_step_4
2023/01/30 11:30:42 Executing step ID: acb_step_5. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:30:42 Launching container with name: acb_step_5
sha256:8f990f3de1333c7a1c803c8db741fc08e573f3b831c42eb566be5dbfc5314511
2023/01/30 11:30:47 Successfully executed container: acb_step_5
2023/01/30 11:30:47 Executing step ID: acb_step_6. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:30:47 Launching container with name: acb_step_6
{
   "schemaVersion": 2,
   "mediaType": "application/vnd.docker.distribution.manifest.list.v2+json",
   "manifests": [
      {
         "mediaType": "application/vnd.docker.distribution.manifest.v2+json",
         "size": 529,
         "digest": "sha256:47dbf6652bc30ab4793046993624be9957246ca7e13283f6ec6abee297f6776f",
         "platform": {
            "architecture": "arm64",
            "os": "linux",
            "variant": "v8"
         }
      },
      {
         "mediaType": "application/vnd.docker.distribution.manifest.v2+json",
         "size": 529,
         "digest": "sha256:47dbf6652bc30ab4793046993624be9957246ca7e13283f6ec6abee297f6776f",
         "platform": {
            "architecture": "arm64",
            "os": "linux",
            "variant": "v8"
         }
      }
   ]
}
2023/01/30 11:30:48 Successfully executed container: acb_step_6
2023/01/30 11:30:48 Step ID: acb_step_0 marked as successful (elapsed time in seconds: 10.313408)
2023/01/30 11:30:48 Populating digests for step ID: acb_step_0...
2023/01/30 11:30:50 Successfully populated digests for step ID: acb_step_0
2023/01/30 11:30:50 Step ID: acb_step_1 marked as successful (elapsed time in seconds: 1.779662)
2023/01/30 11:30:50 Step ID: acb_step_2 marked as successful (elapsed time in seconds: 1.278815)
2023/01/30 11:30:50 Populating digests for step ID: acb_step_2...
2023/01/30 11:30:51 Successfully populated digests for step ID: acb_step_2
2023/01/30 11:30:51 Step ID: acb_step_3 marked as successful (elapsed time in seconds: 1.167488)
2023/01/30 11:30:51 Step ID: acb_step_4 marked as successful (elapsed time in seconds: 1.066252)
2023/01/30 11:30:51 Step ID: acb_step_5 marked as successful (elapsed time in seconds: 5.321173)
2023/01/30 11:30:51 Step ID: acb_step_6 marked as successful (elapsed time in seconds: 1.060950)
2023/01/30 11:30:51 The following dependencies were found:
2023/01/30 11:30:51 
- image:
    registry: estargz.azurecr.io
    repository: multi-multi/aem
    tag: arm
    digest: sha256:47dbf6652bc30ab4793046993624be9957246ca7e13283f6ec6abee297f6776f
  runtime-dependency:
    registry: registry.hub.docker.com
    repository: library/ubuntu
    tag: latest
    digest: sha256:27cb6e6ccef575a4698b66f5de06c7ecd61589132d5a91d098f7f3f9285415a9
  git: {}
- image:
    registry: estargz.azurecr.io
    repository: multi-multi/aem
    tag: x64
    digest: sha256:47dbf6652bc30ab4793046993624be9957246ca7e13283f6ec6abee297f6776f
  runtime-dependency:
    registry: registry.hub.docker.com
    repository: library/ubuntu
    tag: latest
    digest: sha256:27cb6e6ccef575a4698b66f5de06c7ecd61589132d5a91d098f7f3f9285415a9
  git: {}


Run ID: cb1q was successful after 28s

```

The manifest is multi-arch - but both are arm64. 

```json
{
   "schemaVersion": 2,
   "mediaType": "application/vnd.docker.distribution.manifest.list.v2+json",
   "manifests": [
      {
         "mediaType": "application/vnd.docker.distribution.manifest.v2+json",
         "size": 529,
         "digest": "sha256:47dbf6652bc30ab4793046993624be9957246ca7e13283f6ec6abee297f6776f",
         "platform": {
            "architecture": "arm64",
            "os": "linux",
            "variant": "v8"
         }
      },
      {
         "mediaType": "application/vnd.docker.distribution.manifest.v2+json",
         "size": 529,
         "digest": "sha256:47dbf6652bc30ab4793046993624be9957246ca7e13283f6ec6abee297f6776f",
         "platform": {
            "architecture": "arm64",
            "os": "linux",
            "variant": "v8"
         }
      }
   ]
}
```

take #2
=======

```bash
az acr run -g ak-estargz -r estargz -f task-arm.yaml .
Packing source code into tar to upload...
Excluding '.gitignore' based on default ignore rules
Excluding '.git' based on default ignore rules
Uploading archived source code from '/var/folders/c_/dqhl6r4n179dqqmk_9chgkz00000gn/T/cli_source_archive_cd41ca76497c4aaa8ddd1fc115deaba5.tar.gz'...
Sending context (6.652 KiB) to registry: estargz...
Queued a run with ID: cb1r
Waiting for an agent...
2023/01/30 11:34:19 Downloading source code...
2023/01/30 11:34:20 Finished downloading source code
2023/01/30 11:34:20 Alias support enabled for version >= 1.1.0, please see https://aka.ms/acr/tasks/task-aliases for more information.
2023/01/30 11:34:20 Creating Docker network: acb_default_network, driver: 'bridge'
2023/01/30 11:34:20 Successfully set up Docker network: acb_default_network
2023/01/30 11:34:20 Setting up Docker configuration...
2023/01/30 11:34:21 Successfully set up Docker configuration
2023/01/30 11:34:21 Logging in to registry: estargz.azurecr.io
2023/01/30 11:34:22 Successfully logged into estargz.azurecr.io
2023/01/30 11:34:22 Executing step ID: acb_step_0. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:34:22 Scanning for dependencies...
2023/01/30 11:34:22 Successfully scanned dependencies
2023/01/30 11:34:22 Launching container with name: acb_step_0
Sending build context to Docker daemon  52.74kB
Step 1/2 : FROM ubuntu
latest: Pulling from library/ubuntu
10175de2f0c4: Pulling fs layer
10175de2f0c4: Verifying Checksum
10175de2f0c4: Download complete
10175de2f0c4: Pull complete
Digest: sha256:27cb6e6ccef575a4698b66f5de06c7ecd61589132d5a91d098f7f3f9285415a9
Status: Downloaded newer image for ubuntu:latest
 ---> 4c2c87c6c36e
Step 2/2 : CMD ["uname", "-a"]
 ---> [Warning] The requested image's platform (linux/arm64/v8) does not match the detected host platform (linux/amd64) and no specific platform was requested
 ---> Running in 48421a873437
Removing intermediate container 48421a873437
 ---> c6643bd904e7
Successfully built c6643bd904e7
Successfully tagged estargz.azurecr.io/multi-multi/aem:arm
2023/01/30 11:34:27 Successfully executed container: acb_step_0
2023/01/30 11:34:27 Executing step ID: acb_step_1. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:34:27 Pushing image: estargz.azurecr.io/multi-multi/aem:arm, attempt 1
The push refers to repository [estargz.azurecr.io/multi-multi/aem]
80ac6c107b7b: Preparing
80ac6c107b7b: Layer already exists
arm: digest: sha256:552ab2142fcb3eb39e71b30918bbe550e62ce6064edb6abc5809877a1a65f4b8 size: 529
2023/01/30 11:34:28 Successfully pushed image: estargz.azurecr.io/multi-multi/aem:arm
2023/01/30 11:34:28 Step ID: acb_step_0 marked as successful (elapsed time in seconds: 5.051410)
2023/01/30 11:34:28 Populating digests for step ID: acb_step_0...
2023/01/30 11:34:30 Successfully populated digests for step ID: acb_step_0
2023/01/30 11:34:30 Step ID: acb_step_1 marked as successful (elapsed time in seconds: 1.796907)
2023/01/30 11:34:30 The following dependencies were found:
2023/01/30 11:34:30 
- image:
    registry: estargz.azurecr.io
    repository: multi-multi/aem
    tag: arm
    digest: sha256:552ab2142fcb3eb39e71b30918bbe550e62ce6064edb6abc5809877a1a65f4b8
  runtime-dependency:
    registry: registry.hub.docker.com
    repository: library/ubuntu
    tag: latest
    digest: sha256:27cb6e6ccef575a4698b66f5de06c7ecd61589132d5a91d098f7f3f9285415a9
  git: {}

Run ID: cb1r was successful after 12s
```

```bash

$ az acr run -g ak-estargz -r estargz -f task-x64.yaml .
Packing source code into tar to upload...
Excluding '.gitignore' based on default ignore rules
Excluding '.git' based on default ignore rules
Uploading archived source code from '/var/folders/c_/dqhl6r4n179dqqmk_9chgkz00000gn/T/cli_source_archive_4b00d39639b54b0a94ee45ea6754f9f5.tar.gz'...
Sending context (6.941 KiB) to registry: estargz...
Queued a run with ID: cb1s
Waiting for an agent...
2023/01/30 11:35:03 Downloading source code...
2023/01/30 11:35:04 Finished downloading source code
2023/01/30 11:35:04 Alias support enabled for version >= 1.1.0, please see https://aka.ms/acr/tasks/task-aliases for more information.
2023/01/30 11:35:04 Creating Docker network: acb_default_network, driver: 'bridge'
2023/01/30 11:35:04 Successfully set up Docker network: acb_default_network
2023/01/30 11:35:04 Setting up Docker configuration...
2023/01/30 11:35:05 Successfully set up Docker configuration
2023/01/30 11:35:05 Logging in to registry: estargz.azurecr.io
2023/01/30 11:35:06 Successfully logged into estargz.azurecr.io
2023/01/30 11:35:06 Executing step ID: acb_step_0. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:35:06 Scanning for dependencies...
2023/01/30 11:35:07 Successfully scanned dependencies
2023/01/30 11:35:07 Launching container with name: acb_step_0
Sending build context to Docker daemon  56.32kB
Step 1/2 : FROM ubuntu
latest: Pulling from library/ubuntu
6e3729cf69e0: Pulling fs layer
6e3729cf69e0: Verifying Checksum
6e3729cf69e0: Download complete
6e3729cf69e0: Pull complete
Digest: sha256:27cb6e6ccef575a4698b66f5de06c7ecd61589132d5a91d098f7f3f9285415a9
Status: Downloaded newer image for ubuntu:latest
 ---> 6b7dfa7e8fdb
Step 2/2 : CMD ["uname", "-a"]
 ---> Running in de31b3a15892
Removing intermediate container de31b3a15892
 ---> 600240f6bf83
Successfully built 600240f6bf83
Successfully tagged estargz.azurecr.io/multi-multi/aem:x64
2023/01/30 11:35:12 Successfully executed container: acb_step_0
2023/01/30 11:35:12 Executing step ID: acb_step_1. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:35:12 Pushing image: estargz.azurecr.io/multi-multi/aem:x64, attempt 1
The push refers to repository [estargz.azurecr.io/multi-multi/aem]
6515074984c6: Preparing
6515074984c6: Layer already exists
x64: digest: sha256:3e449ff54b7ae52488147be4b4fa36ad9c5b4cff9303852221ce814c779b6758 size: 529
2023/01/30 11:35:14 Successfully pushed image: estargz.azurecr.io/multi-multi/aem:x64
2023/01/30 11:35:14 Step ID: acb_step_0 marked as successful (elapsed time in seconds: 5.451232)
2023/01/30 11:35:14 Populating digests for step ID: acb_step_0...
2023/01/30 11:35:15 Successfully populated digests for step ID: acb_step_0
2023/01/30 11:35:15 Step ID: acb_step_1 marked as successful (elapsed time in seconds: 1.759240)
2023/01/30 11:35:15 The following dependencies were found:
2023/01/30 11:35:15 
- image:
    registry: estargz.azurecr.io
    repository: multi-multi/aem
    tag: x64
    digest: sha256:3e449ff54b7ae52488147be4b4fa36ad9c5b4cff9303852221ce814c779b6758
  runtime-dependency:
    registry: registry.hub.docker.com
    repository: library/ubuntu
    tag: latest
    digest: sha256:27cb6e6ccef575a4698b66f5de06c7ecd61589132d5a91d098f7f3f9285415a9
  git: {}


Run ID: cb1s was successful after 13s
```

```bash

az acr run -g ak-estargz -r estargz -f task.yaml .
Packing source code into tar to upload...
Excluding '.gitignore' based on default ignore rules
Excluding '.git' based on default ignore rules
Uploading archived source code from '/var/folders/c_/dqhl6r4n179dqqmk_9chgkz00000gn/T/cli_source_archive_f4cd7d87d1654655aa36e8d3af10758e.tar.gz'...
Sending context (7.297 KiB) to registry: estargz...
Queued a run with ID: cb1t
Waiting for an agent...
2023/01/30 11:35:51 Downloading source code...
2023/01/30 11:35:52 Finished downloading source code
2023/01/30 11:35:53 Alias support enabled for version >= 1.1.0, please see https://aka.ms/acr/tasks/task-aliases for more information.
2023/01/30 11:35:53 Creating Docker network: acb_default_network, driver: 'bridge'
2023/01/30 11:35:54 Successfully set up Docker network: acb_default_network
2023/01/30 11:35:54 Setting up Docker configuration...
2023/01/30 11:35:54 Successfully set up Docker configuration
2023/01/30 11:35:54 Logging in to registry: estargz.azurecr.io
2023/01/30 11:35:55 Successfully logged into estargz.azurecr.io
2023/01/30 11:35:55 Executing step ID: acb_step_0. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:35:55 Launching container with name: acb_step_0
Created manifest list estargz.azurecr.io/multi-multi/aem:multi
2023/01/30 11:35:56 Successfully executed container: acb_step_0
2023/01/30 11:35:56 Executing step ID: acb_step_1. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:35:56 Launching container with name: acb_step_1
sha256:8bbb307f60ac2813f536fd24c0200d03080144cbf20fbf4a1998ea1505847f82
2023/01/30 11:35:57 Successfully executed container: acb_step_1
2023/01/30 11:35:57 Executing step ID: acb_step_2. Timeout(sec): 600, Working directory: '', Network: 'acb_default_network'
2023/01/30 11:35:57 Launching container with name: acb_step_2
{
   "schemaVersion": 2,
   "mediaType": "application/vnd.docker.distribution.manifest.list.v2+json",
   "manifests": [
      {
         "mediaType": "application/vnd.docker.distribution.manifest.v2+json",
         "size": 529,
         "digest": "sha256:552ab2142fcb3eb39e71b30918bbe550e62ce6064edb6abc5809877a1a65f4b8",
         "platform": {
            "architecture": "arm64",
            "os": "linux",
            "variant": "v8"
         }
      },
      {
         "mediaType": "application/vnd.docker.distribution.manifest.v2+json",
         "size": 529,
         "digest": "sha256:3e449ff54b7ae52488147be4b4fa36ad9c5b4cff9303852221ce814c779b6758",
         "platform": {
            "architecture": "amd64",
            "os": "linux"
         }
      }
   ]
}
2023/01/30 11:35:59 Successfully executed container: acb_step_2
2023/01/30 11:35:59 Step ID: acb_step_0 marked as successful (elapsed time in seconds: 1.158361)
2023/01/30 11:35:59 Step ID: acb_step_1 marked as successful (elapsed time in seconds: 1.384460)
2023/01/30 11:35:59 Step ID: acb_step_2 marked as successful (elapsed time in seconds: 1.149651)

Run ID: cb1t was successful after 8s


```

This time the manifest is multi-arch pointing correctly.

```json
{
   "schemaVersion": 2,
   "mediaType": "application/vnd.docker.distribution.manifest.list.v2+json",
   "manifests": [
      {
         "mediaType": "application/vnd.docker.distribution.manifest.v2+json",
         "size": 529,
         "digest": "sha256:552ab2142fcb3eb39e71b30918bbe550e62ce6064edb6abc5809877a1a65f4b8",
         "platform": {
            "architecture": "arm64",
            "os": "linux",
            "variant": "v8"
         }
      },
      {
         "mediaType": "application/vnd.docker.distribution.manifest.v2+json",
         "size": 529,
         "digest": "sha256:3e449ff54b7ae52488147be4b4fa36ad9c5b4cff9303852221ce814c779b6758",
         "platform": {
            "architecture": "amd64",
            "os": "linux"
         }
      }
   ]
}
```
