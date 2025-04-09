Tiny Rust lib and tool for Matter Setup Payload and QRCode generation

## Usage
```shell
generate_setup_payload [OPTIONS] --vendor-id <VENDOR_ID> --product-id <PRODUCT_ID> --discriminator <DISCRIMINATOR> --passcode <PASSCODE>

Options:
      --vendor-id <VENDOR_ID>                          
      --product-id <PRODUCT_ID>                        
      --discriminator <DISCRIMINATOR>                  
      --passcode <PASSCODE>                            
  -c, --commissioning-flow <COMMISSIONING_FLOW>        [default: 0]
      --discovery-cap-bitmask <DISCOVERY_CAP_BITMASK>  [default: 2]
  -s, --save-qrcode                                    Save an QRCode image in PNG to local

parse_setup_payload [OPTIONS] <QRCODE>

Arguments:
  <QRCODE>  

Options:
  -s, --save-qrcode  
```

## Example
```shell
./generate_setup_payload --vendor-id 114 --product-id 514 --discriminator 810 --passcode 1919 -s
Manualcode : 05107100002
QRCode     : MT:4U4J000S02PIYH00000
```
![4U4J000S02PIYH00000](https://github.com/user-attachments/assets/50010003-10b1-4a4d-b424-cfc586c52f90)
```shell
./parse_setup_payload MT:4U4J000S02PIYH00000
Flow                   : 0
Passcode               : 1919
Short Discriminator    : 3
Long Discriminator     : 810
Discovery Capabilities : 2
Vendor Id              : 114   (0x0072)
Product Id             : 514   (0x0202)
ManualCode             : 05107100002
```
