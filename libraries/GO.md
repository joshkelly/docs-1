<!-- <meta>
{
    "title":"Go",
    "slug":"go",
    "description":"An official Golang client for the Packet API",
    "author":"Zalkar Ziiaidin",
    "github":"zalkar-z",
    "date": "2019/12/11",
    "tag":["Go", "CLI"]
}
</meta> -->

![Packet Go API Client Banner](/images/libraries/go/go-banner.png)

Welcome to [Packet Go API Client](https://github.com/packethost/packngo).

This is a library to help you consume our API routes effectively, making your experience as a developer with Packet a breeze!

For more information about our API endpoints, please visit our [API Documentation](https://www.packet.com/developers/api/).

## Installation

`go get github.com/packethost/packngo`

## Usage

To authenticate to the Packet API, you must have your API token exported in env var `PACKET_AUTH_TOKEN`.

This code snippet initializes Packet API client, and lists your Projects:

```
package main

import (
	"log"

	"github.com/packethost/packngo"
)

func main() {
	c, err := packngo.NewClient()
	if err != nil {
		log.Fatal(err)
	}

	ps, _, err := c.Projects.List(nil)
	if err != nil {
		log.Fatal(err)
	}
	for _, p := range ps {
		log.Println(p.ID, p.Name)
	}
}
```

This lib is used by the official [terraform-provider-packet](https://github.com/terraform-providers/terraform-provider-packet).

You can also learn a lot from the `*_test.go` sources. Almost all out tests touch the Packet API, so you can see how auth, querying and POSTing works. For example [devices_test.go](https://github.com/packethost/packngo/blob/master/devices_test.go).

## Routes & Methods

For more information on available router and methods, please visit [Packet Golang CLI public repo](https://github.com/packethost/packngo).

