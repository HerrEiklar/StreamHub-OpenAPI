# Unimplemented Models

## User

### Why hasn't it been implemented?

Because the User API itself wasn't implemented in the first place

### The Model

```yaml User_Model
User:
  type: object
  title: User
  deprecated: true
  x-tags:
    - user
  properties:
    id:
      type: integer
      format: int32
      maximum: 999999
      readOnly: true
    username:
      type: string
      minLength: 2
      pattern: '^[^@#:`]+$'
      maxLength: 32
    discriminator:
      type: string
      format: int32
      minLength: 4
      maxLength: 4
      pattern: '^[0-9]*$'
      readOnly: true
    locale:
      type: string
      minLength: 2
      maxLength: 2
      enum:
        - de
        - en
      pattern: '^[A-Za-z0-9]+$'
    veified:
      type: boolean
      default: false
      readOnly: true
    email:
      type: string
      pattern: '/^(?:[a-z0-9!#$%&''*+\/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&''*+\/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])$/g'
      maxLength: 2000
    firstName:
      type: string
      pattern: '/^[a-zA-ZàáâäãåąčćęèéêëėįìíîïłńòóôöõøùúûüųūÿýżźñçčšžÀÁÂÄÃÅĄĆČĖĘÈÉÊËÌÍÎÏĮŁŃÒÓÔÖÕØÙÚÛÜŲŪŸÝŻŹÑßÇŒÆČŠŽ∂ð ,.''-]+$/u'
      maxLength: 100
    lastName:
      type: string
      pattern: '/^[a-zA-ZàáâäãåąčćęèéêëėįìíîïłńòóôöõøùúûüųūÿýżźñçčšžÀÁÂÄÃÅĄĆČĖĘÈÉÊËÌÍÎÏĮŁŃÒÓÔÖÕØÙÚÛÜŲŪŸÝŻŹÑßÇŒÆČŠŽ∂ð ,.''-]+$/u'
      maxLength: 100
  required:
    - username
    - discriminator
```