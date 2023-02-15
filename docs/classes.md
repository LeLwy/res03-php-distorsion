# Classes :

## Router :

    - class Router :

        - Methods :
        
            - private function parseRequest
            - public function route
            
## Models :

    - class User : 
        
        - Attributes :
        
            - private int $id
            - private string $username
            - private string $email
            - private string $password
            
        - Constructor(string $username, string $email, string $password)
        
        - Methods :
        
            - Public accessors for each attributes

    - class Channel : 
        
        - Attributes :
        
            - private int $id
            - private string $name
            - private int $categoryId
            - private array $posts
            
        - Constructor(string $name, Category $categoryId)
        
        - Methods :
        
            - Public accessors for each attributes

    - class Post : 
        
        - Attributes :
        
            - private int $id
            - private string $content
            - private User $author
            - private int $channelId
            
        - Constructor(string $content, User $author, int $channelId)
        
        - Methods :
        
            - Public accessors for each attributes

    - class Category : 
        
        - Attributes :
        
            - private int $id
            - private string $name
            - private string description
            - private array $channels
            
        - Constructor(string $name, string description)
        
        - Methods :
        
            - Public accessors for each attributes
            
## Managers :

    - abstract class AbstractManager :

        - Attributes :

            - protected PDO $db
            - protected string $dbName
            - protected string $port
            - protected string $host
            - protected string $username
            - protected string $password

        - Methods :

            - private function initDb() // initie la base de données
        
        
    - class UserManager extends AbstractManager :
        
        - Constructor(string $dbName, string $port, string $host, string $username, string $password)
        
        - Methods :
        
            - getAllUsers()
            - getUserById()
            - insertUser()
            - editUser()
            
            
    - class ChannelManager extends AbstractManager :
        
        - Constructor(string $dbName, string $port, string $host, string $username, string $password)
        
        - Methods :
        
            - getAllChannels()
            - getChannelByName()
            - insertChannel()
            - editChannel()
            
            
    - class PostManager extends AbstractManager :
        
        - Constructor(string $dbName, string $port, string $host, string $username, string $password)
        
        - Methods :
        
            - insertPost()
            - editPost()
            - getPostsByChannelId()
            
            
    - class CategoryManager extends AbstractManager :
        
        - Constructor(string $dbName, string $port, string $host, string $username, string $password)
        
        - Methods :
        
            - getAllCategories()
            - getCategoryById()
            - insertCategory()
            - editCategory()
            
## Controllers :

    - class UserController :
        
        - Attributes :
        
            - private UserManager $manager
            
        - Methods : 
        
            - index() // appelle le bon template

    - class ChannelController :
        
        - Attributes :
        
            - private ChannelManager $manager
            
        - Methods : 
        
            - index() // appelle le bon template

    - class PostController :
        
        - Attributes :
        
            - private PostManager $manager
            
        - Methods : 
        
            - index() // appelle le bon template

    - class CategoryController :
        
        - Attributes :
        
            - private CategoryManager $manager
            
        - Methods : 
        
            - index() // appelle le bon template
            
        
    