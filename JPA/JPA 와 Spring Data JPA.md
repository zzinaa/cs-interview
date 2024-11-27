Q. JPA와 Spring Data Jpa의 차이점이 무엇인가요?
A. JPA는 자바 진영의 ORM 표준으로 채택된 인터페이스입니다. Hibernate 같은 경우 이런 JPA를 구현한 구현체중 하나 입니다.  
Spring Data Jpa의 경우 Spring에서 JPA 기반 개발을 더 편하게 할 수 있게 제공하는 라이브러리 입니다.  
Repository를 통해 편리하게 다양한 기능을 사용할 수 있습니다.  

## JPA 란?
JPA(Java Persistence API)는 Java 진영의 ORM 기술 표준으로 채택된 인터페이스다.

### Hibernate
Hibernate는 JPA의 구현체중 하나다.
JPA의 모든 기능을 지원하며, Hibernate는 객체와 관계형 데이터베이스 간의 매핑을 자동으로 처리해서 개발자가 일일이 SQL 쿼리를 작성하지 않도록 도와줌  


## Spring Data JPA  
Spring Data JPA는 Spring에서 제공하여 JPA 기반 애플리케이션 개발을 보다 간편하게 만드는 라이브러리/프레임워크이다. 
Spring Data JPA의 경우 Repository라는 인터페이스를 제공함으로써 이루어진다.  

Repository를 통해 다양한 기능을 쉽게 사용할 수 있다.  
```
@Repository
public interface UserRepository extends JpaRepository<User, Long> {}

@Service
public class UserService {

    @Autowired
    private UserRepository userRepository;

    public List<User> findAll() {
        return userRepository.findAll();
    }

     public Optional<User> findById(Long id) {
        return userRepository.findById(id);
    }

    public List<User> findByName(String name) {
        return userRepository.findByName(name);
    }

     public User save(User user) {
        return userRepository.save(user);
    }
}
```