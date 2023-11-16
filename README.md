# AWS Auto Tag Website
The Whole AWS services is <span style="color:red;">stopped </span> due to student account limit.(2023/10/01)

This is a back-end based school project, all code source is <span style="color:red;">hidden </span> due to Monash University policy.(2023/11/16)

## Demo & Report:

Please read Project Report.pdf

## architecture diagram:

![Alt text](src/architect.png)
[https://lucid.app/lucidchart/f4bcd10f-9f25-4f62-89f3-0867bc80d665/edit?viewport_loc=-156%2C286%2C1579%2C783%2C11Z2evwRBl31&amp;invitationId=inv_b5358056-2f9a-455b-961a-c507f7692c75](https://lucid.app/lucidchart/f4bcd10f-9f25-4f62-89f3-0867bc80d665/edit?viewport_loc=-156%2C286%2C1579%2C783%2C11Z2evwRBl31&invitationId=inv_b5358056-2f9a-455b-961a-c507f7692c75)

## AWS services APIs

### upload image

- API:  `https://rhnlx9ogtj.execute-api.us-east-1.amazonaws.com/pd/image`
- method: **POST**
- request JSON example: `{"name":"image.jpg","file":"/9j/4AAQSkZJRgABAQEASABIAAD/2w....","user_id": "c60e1129-e6b5-4f43-803f-95287e91a210"}`
- return JSON example: `{"name": "images/acdd49a6fe1011eda7a9b2705f222ada.jpg"}`

### find by tag

- API:  `https://rhnlx9ogtj.execute-api.us-east-1.amazonaws.com/pd/findbytag`
- method: **POST**
- request JSON example:
  ```
  {
      "tags": [
          {
              "tag": "person",
              "count": 1
          },
  	{
  	    "tag": "bus",
  	    "count": 1
  	}
      ],
      "user_id": "c60e1129-e6b5-4f43-803f-95287e91a210"
  }
  ```
- return JSON example:
  ```
  {
      "links": [
          "https://a3-image.s3.amazonaws.com/images/10411618021111eebf162e6becab08fd.jpg?AWSAccessKeyId=ASIA2LDBP3IS3ZLGUIH2&Signature=S2qAqXHereEJaUFRexl57%2FeVTxc%3D&x-amz-security-token=IQoJb3JpZ2luX2VjELb%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJHMEUCIFltOSd3Qf%2FVQUB%2Bbd%2BsPYfQBjf55WWNBivrJFB5rL%2FsAiEA0NwZzKApctSCoBVUaCUZW9MFn0VySukypO80iukJC7Aq%2FQII7v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw3MTEwMjE1NTAxMTciDO5Hjl5%2F7U3%2BT70ZkyrRAnUmEESxq%2BrBpc6h%2FRybZz9KMMkO%2FYt5bvSsQ9jYQGBbVHaQtw61fj2XekiyXoF%2BTvqc%2B5Hiphx19bZVTCeeNPhCe2RfRccKCJPrcL1eb8l7nv3oSOb9iRG7wcl0GljhO2%2FSI0%2FHQveaR16RyfHUtgL8S1zna0rC0cqiBoF9xcS42dkGbtVUnBVq78O4vBAo12EZbQb5hIlltNyitxNGlAej4dYGcM%2FGbXjjJQ2yXXlh2Jix8wdkhfvcjOeKKTbBMAWqhmVXAJmn5vFfk8pl58nXFJm2Nwa9sy6tf8SdAvuB%2BjYk4zBxh2kFckGr0M1Px%2BBujpDVnXailcG1aI7W5laGZtsSHnEsRxg0HE4m4YtmoVztqXN01KaDs%2BawQYBiRR8XsDQjoexiAvhyrGhIYP943BMDoTL1RbciFBikhChrwG8qXqycESOiGVaC2yzLRQEwgPfsowY6ngHAnoJ5ZoIJJ2thxarP%2BpY1OgRiB73QL7EdL%2BT1uCI4EkhKfmPIQWW2BzfiTI%2BqTvB5hpXHZKJu0iC83Ks939trgNnrHqHu8ef5gN1eZrOFETKtXT2aaH3E3Kds3cEsMGwyk5yONTEp3TLyKG458n7iGA6xZHj5jn3WT7gSvYVSbqb7%2F167qyEPUrZeG9EOnYOEHXFKFodddTIhnd2XAw%3D%3D&Expires=1685798997"
      ]
  }
  ```

### find by image

- API:  `https://rhnlx9ogtj.execute-api.us-east-1.amazonaws.com/pd/findbyimage`
- method: **POST**
- request JSON example:
  ```
  {
      "image": "/9j/4AAQSkZJRgABAQEASABIAAD/2w....",
      "user_id": "c60e1129-e6b5-4f43-803f-95287e91a210"
  }
  ```
- return JSON example:
  ```
  {
      "links": [
          "https: //a3-image.s3.amazonaws.com/images/10411618021111eebf162e6becab08fd.jpg?AWSAccessKeyId=ASIA2LDBP3IS3ZLGUIH2&Signature=S2qAqXHereEJaUFRexl57%2FeVTxc%3D&x-amz-security-token=IQoJb3JpZ2luX2VjELb%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJHMEUCIFltOSd3Qf%2FVQUB%2Bbd%2BsPYfQBjf55WWNBivrJFB5rL%2FsAiEA0NwZzKApctSCoBVUaCUZW9MFn0VySukypO80iukJC7Aq%2FQII7v%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARAAGgw3MTEwMjE1NTAxMTciDO5Hjl5%2F7U3%2BT70ZkyrRAnUmEESxq%2BrBpc6h%2FRybZz9KMMkO%2FYt5bvSsQ9jYQGBbVHaQtw61fj2XekiyXoF%2BTvqc%2B5Hiphx19bZVTCeeNPhCe2RfRccKCJPrcL1eb8l7nv3oSOb9iRG7wcl0GljhO2%2FSI0%2FHQveaR16RyfHUtgL8S1zna0rC0cqiBoF9xcS42dkGbtVUnBVq78O4vBAo12EZbQb5hIlltNyitxNGlAej4dYGcM%2FGbXjjJQ2yXXlh2Jix8wdkhfvcjOeKKTbBMAWqhmVXAJmn5vFfk8pl58nXFJm2Nwa9sy6tf8SdAvuB%2BjYk4zBxh2kFckGr0M1Px%2BBujpDVnXailcG1aI7W5laGZtsSHnEsRxg0HE4m4YtmoVztqXN01KaDs%2BawQYBiRR8XsDQjoexiAvhyrGhIYP943BMDoTL1RbciFBikhChrwG8qXqycESOiGVaC2yzLRQEwgPfsowY6ngHAnoJ5ZoIJJ2thxarP%2BpY1OgRiB73QL7EdL%2BT1uCI4EkhKfmPIQWW2BzfiTI%2BqTvB5hpXHZKJu0iC83Ks939trgNnrHqHu8ef5gN1eZrOFETKtXT2aaH3E3Kds3cEsMGwyk5yONTEp3TLyKG458n7iGA6xZHj5jn3WT7gSvYVSbqb7%2F167qyEPUrZeG9EOnYOEHXFKFodddTIhnd2XAw%3D%3D&Expires=1685798997"
      ],
      "tags": [
          "person"
      ]
  }
  ```

### Manual change tags

- API:  `https://rhnlx9ogtj.execute-api.us-east-1.amazonaws.com/pd/manualchangetag`
- method: **POST**
- request JSON example:
  ```
  {
      "url": "https://a3-image.s3.amazonaws.com/images/acdd49a6fe1011eda7a9b2705f222ada.jpg",
      "type": 1,
      "tags": [
          {
              "tag": "person",
              "count": 2
          },
          {
              "tag": "alex",
              "count": 1
          }
      ]
  }
  ```
- return JSON example: `{"Tags updated successfully"}`

### Delete image

- API:  `https://rhnlx9ogtj.execute-api.us-east-1.amazonaws.com/pd/deleteimage`
- method: **DELETE**
- request JSON eample:`{"url":"https://a3-image.s3.amazonaws.com/images/abcdabcd.jpg"}`
- return JSON example: `{"Image successfully deleted"}`

### Show All Images

- API:  `https://rhnlx9ogtj.execute-api.us-east-1.amazonaws.com/pd/showallimages`
- method: **POST**
- request JSON example: `{"user_id": "c60e1129-e6b5-4f43-803f-95287e91a210"}`
- return JSON example:
  ```
  {
      "images": [
          {
              "url": "https://a3-image.s3.amazonaws.com/images/4c039c18039511ee9d29fee879db0a70.jpg?AWSAcc...",
              "tags": [
                  {
                      "count": 1.0,
                      "tag": "bus"
                  },
                  {
                      "count": 1.0,
                      "tag": "person"
                  }
              ]
          },
          {
              "url": "https://a3-image.s3.amazonaws.com/images/125d1...",
              "tags": [
                  {
                      "count": 1.0,
                      "tag": "bus"
                  },
                  {
                      "count": 1.0,
                      "tag": "person"
                  }
              ]
          }
      ]
  }
  ```

---

NOTE: In the top 3 APIs, you need include user_id in request body. Following is an example to decode id_token and get user_id(**sub**).

```
import jwt

id_token = "id_token"
payload = jwt.decode(id_token, options={"verify_signature": False})

print(payload["sub"])
```

A helpful website to decode id_token:

[http://calebb.net/](http://calebb.net/)

---
