# Database :

## Tables :

    - users :
        
        - id            int A.I
        - username      varchar (255)
        - email         varchar (255)
        - password      varchar (255)
        
    - channels :

        - id            int A.I
        - name          varchar (255)
        - category      int FK

    - posts :

        - id            int A.I
        - author        int FK
        - content       varchar (1023)
        - channel       int FK

    - categories :

        - id            int A.I
        - name          varchar (255)
        - description   varchar (511)
        
## Relations :

    - channels :

        - category      int FK -> categories : id

    - posts :

        - author        int FK -> users : id
        - channel_Id    int FK -> channels : id

    