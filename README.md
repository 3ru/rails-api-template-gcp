## Upload image to gcp clound storage by using rails api

1. make api key and put it on `/app/key/[gcpkey.json]`  
  (ofc, no key file in this repository)

2. Uncomment out the GCP section.  
   (Since there is no storage.yml in this repository, u need to create it `config/storage.yml`)
  ```
  google:
    service: GCS
    project: hoge
    credentials: <%= Rails.root.join("./key/gcpkey.json") %>
    bucket: hoge
  ```



- Can also switch to saving to local.
```
  - config.active_storage.service = :google
  + config.active_storage.service = :local
```

### Prob
- Cannot be saved at the same time as normal data.
