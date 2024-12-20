# Estrutura do Projeto

```
metakyasshu/
├── pom.xml
├── Dockerfile
├── compose.yaml
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── metakyasshuapi/
│   │   │   │   ├── controller/
│   │   │   │   │   ├── AuthenticateController
│   │   │   │   │   ├── BalanceController
│   │   │   │   │   ├── CardController
│   │   │   │   │   ├── CategoryController
│   │   │   │   │   ├── CollaboratorController
│   │   │   │   │   ├── ExpenseController
│   │   │   │   │   ├── GoalController
│   │   │   │   │   ├── InvitationController
│   │   │   │   │   ├── ParticipantController
│   │   │   │   │   ├── PaymentController
│   │   │   │   │   └── UserController
│   │   │   │   ├── model/
│   │   │   │   │   ├── authenticate/
│   │   │   │   │   │   ├── Login
│   │   │   │   │   │   └── Token
│   │   │   │   │   ├── balance/
│   │   │   │   │   │   ├── entity/
│   │   │   │   │   │   │   └── Balance
│   │   │   │   │   │   ├── mapper/
│   │   │   │   │   │   │   └── BalanceMapper
│   │   │   │   │   │   └── module/
│   │   │   │   │   │       ├── BalanceDto
│   │   │   │   │   │       ├── BalanceFilter
│   │   │   │   │   │       └── BalanceService
│   │   │   │   │   ├── card/
│   │   │   │   │   │   ├── entity/
│   │   │   │   │   │   │   └── Card
│   │   │   │   │   │   ├── mapper/
│   │   │   │   │   │   │   └── CardMapper
│   │   │   │   │   │   └── module/
│   │   │   │   │   │       ├── CardDto
│   │   │   │   │   │       ├── CardFilter
│   │   │   │   │   │       ├── CardForm
│   │   │   │   │   │       └── CardSummarized
│   │   │   │   │   ├── category/
│   │   │   │   │   │   ├── entity/
│   │   │   │   │   │   │   ├── Category
│   │   │   │   │   │   │   └── CategoryUser
│   │   │   │   │   │   ├── mapper/
│   │   │   │   │   │   │   └── CategoryMapper
│   │   │   │   │   │   └── module/
│   │   │   │   │   │       └── CategoryFormDto
│   │   │   │   │   ├── collaborator/
│   │   │   │   │   │   ├── entity/
│   │   │   │   │   │   │   └── Collaborator
│   │   │   │   │   │   ├── mapper/
│   │   │   │   │   │   │   └── CollaboratorMapper
│   │   │   │   │   │   └── module/
│   │   │   │   │   │       ├── CollaboratorDto
│   │   │   │   │   │       └── CollaboratorSummarized
│   │   │   │   │   ├── expense/
│   │   │   │   │   │   ├── entity/
│   │   │   │   │   │   │   └── Expense
│   │   │   │   │   │   ├── mapper/
│   │   │   │   │   │   │   └── ExpenseMapper
│   │   │   │   │   │   └── module/
│   │   │   │   │   │       ├── ExpenseDto
│   │   │   │   │   │       └── ExpenseSummarized
│   │   │   │   │   ├── invitation/
│   │   │   │   │   │   ├── entity/
│   │   │   │   │   │   │   └── Invitation
│   │   │   │   │   │   ├── mapper/
│   │   │   │   │   │   │   └── InvitationMapper
│   │   │   │   │   │   └── module/
│   │   │   │   │   │       └── InvitationSummarized
│   │   │   │   │   ├── participation/
│   │   │   │   │   │   ├── entity/
│   │   │   │   │   │   │   └── Participation
│   │   │   │   │   │   ├── mapper/
│   │   │   │   │   │   │   └── ParticipationMapper
│   │   │   │   │   │   └── module/
│   │   │   │   │   │       ├── ParticipationDto
│   │   │   │   │   │       └── ParticipationForm
│   │   │   │   │   ├── payment/
│   │   │   │   │   │   ├── entity/
│   │   │   │   │   │   │   └── Payment
│   │   │   │   │   │   ├── mapper/
│   │   │   │   │   │   │   └── PaymentMapper
│   │   │   │   │   │   └── module/
│   │   │   │   │   │       ├── PaymentDto
│   │   │   │   │   │       └── PaymentForm
│   │   │   │   │   ├── types/
│   │   │   │   │   │   ├── AccessLevel
│   │   │   │   │   │   ├── Term
│   │   │   │   │   │   ├── TypeCard
│   │   │   │   │   │   ├── TypeCategory
│   │   │   │   │   │   └── TypeExpense
│   │   │   │   │   └── user/
│   │   │   │   │       ├── entity/
│   │   │   │   │       │   ├── Permission
│   │   │   │   │       │   └── User
│   │   │   │   │       ├── mapper/
│   │   │   │   │       │   └── UserMapper
│   │   │   │   │       └── module/
│   │   │   │   │           ├── PasswordForm
│   │   │   │   │           ├── RecoverAccess
│   │   │   │   │           ├── UserDto
│   │   │   │   │           ├── UserFilter
│   │   │   │   │           ├── UserForm
│   │   │   │   │           ├── UserFormEdit
│   │   │   │   │           └── UserSummarized
│   │   │   │   ├── repository/
│   │   │   │   │   ├── BalanceRepository
│   │   │   │   │   ├── CardRepository
│   │   │   │   │   ├── CategoryRepository
│   │   │   │   │   ├── CategoryUserRepository
│   │   │   │   │   ├── CollaboratorRepository
│   │   │   │   │   ├── ExpenseRepository
│   │   │   │   │   ├── GoalRepository
│   │   │   │   │   ├── InvitationRepository
│   │   │   │   │   ├── ParticipationRepository
│   │   │   │   │   ├── PaymentRepository
│   │   │   │   │   └── UserRepository
│   │   │   │   ├── service/
│   │   │   │   │   ├── authenticate/
│   │   │   │   │   │   └── AuthenticateService
│   │   │   │   │   ├── balance/
│   │   │   │   │   │   ├── BalanceDeleteService
│   │   │   │   │   │   ├── BalanceFindService
│   │   │   │   │   │   ├── BalanceSaveService
│   │   │   │   │   │   └── BalanceService
│   │   │   │   │   ├── card/
│   │   │   │   │   │   ├── CardAddService
│   │   │   │   │   │   ├── CardDeleteService
│   │   │   │   │   │   ├── CardFindService
│   │   │   │   │   │   ├── CardService
│   │   │   │   │   │   ├── CardToolService
│   │   │   │   │   │   └── CardUpdateService
│   │   │   │   │   ├── category/
│   │   │   │   │   │   ├── CategoryFindService
│   │   │   │   │   │   ├── CategorySaveService
│   │   │   │   │   │   └── CategoryService
│   │   │   │   │   ├── collaborator/
│   │   │   │   │   │   ├── CollaboratorCreateService
│   │   │   │   │   │   ├── CollaboratorFindService
│   │   │   │   │   │   ├── CollaboratorService
│   │   │   │   │   │   └── CollaboratorUpdateService
│   │   │   │   │   ├── email/
│   │   │   │   │   │   ├── EmailInvitationService
│   │   │   │   │   │   ├── EmailService
│   │   │   │   │   │   ├── EmailUserCreateService
│   │   │   │   │   │   ├── EmailUserRecoverService
│   │   │   │   │   │   ├── InterfaceEmailService
│   │   │   │   │   │   └── SendEmailService
│   │   │   │   │   ├── expense/
│   │   │   │   │   │   ├── ExpenseAddService
│   │   │   │   │   │   ├── ExpenseFindService
│   │   │   │   │   │   ├── ExpenseService
│   │   │   │   │   │   └── ExpenseUpdateService
│   │   │   │   │   ├── goal/
│   │   │   │   │   │   ├── GoalAddService
│   │   │   │   │   │   ├── GoalFindService
│   │   │   │   │   │   ├── GoalService
│   │   │   │   │   │   └── GoalUpdateService
│   │   │   │   │   ├── invitation/
│   │   │   │   │   │   ├── InvitationAcceptService
│   │   │   │   │   │   ├── InvitationFindService
│   │   │   │   │   │   ├── InvitationSendService
│   │   │   │   │   │   └── InvitationService
│   │   │   │   │   ├── jwt/
│   │   │   │   │   │   ├── JwtAuthCreateService
│   │   │   │   │   │   ├── JwtAuthExtractService
│   │   │   │   │   │   └── JwtAuthService
│   │   │   │   │   ├── participant/
│   │   │   │   │   │   ├── ParticipantSaveService
│   │   │   │   │   │   └── ParticipantService
│   │   │   │   │   ├── payment/
│   │   │   │   │   │   ├── PaymentSaveService
│   │   │   │   │   │   └── PaymentService
│   │   │   │   │   ├── tools/
│   │   │   │   │   │   ├── DateService
│   │   │   │   │   │   ├── ImageService
│   │   │   │   │   │   ├── MessageDecode
│   │   │   │   │   │   └── Thymeleaf
│   │   │   │   │   ├── user/
│   │   │   │   │   │   ├── EncapsulatedUserService
│   │   │   │   │   │   ├── ToolsUserService
│   │   │   │   │   │   ├── UserCreateService
│   │   │   │   │   │   ├── UserDeleteService
│   │   │   │   │   │   ├── UserFindService
│   │   │   │   │   │   ├── UserPhotoService
│   │   │   │   │   │   ├── UserSaveService
│   │   │   │   │   │   ├── UserService
│   │   │   │   │   │   ├── UserUpdateService
│   │   │   │   │   │   └── InterfaceService
│   │   │   │   ├── settings/
│   │   │   │   │   ├── bean/
│   │   │   │   │   │   ├── AuthenticationManagerBean
│   │   │   │   │   │   ├── BCryptPasswordEncoderBean
│   │   │   │   │   │   ├── EmailSenderBean
│   │   │   │   │   │   ├── HttpsRedirectConfig.java
│   │   │   │   │   │   └── MessageSourceBean
│   │   │   │   │   ├── exception/
│   │   │   │   │   │   ├── DuplicateException
│   │   │   │   │   │   ├── ErrorDto
│   │   │   │   │   │   ├── ExcludeException
│   │   │   │   │   │   ├── FieldNotFoundException
│   │   │   │   │   │   ├── ImageException
│   │   │   │   │   │   ├── NotFoundException
│   │   │   │   │   │   ├── ParticipationException
│   │   │   │   │   │   ├── ResourceExceptionHandler
│   │   │   │   │   │   ├── UserAuthenticateException
│   │   │   │   │   │   └── UserDisabledException
│   │   │   │   │   ├── security/
│   │   │   │   │   │   ├── AuthenticationFilter
│   │   │   │   │   │   ├── SecurityWebApplication
│   │   │   │   │   │   └── MetakyasshuApiApplication
│   │   │   ├── resources/
│   │   │   │    ├── templates/
│   │   │   │    │    ├── CreateAccount.html
│   │   │   │    │    ├── Invite.html
│   │   │   │    │    ├── RecoverPassword.html
│   │   │   │    │    ├── Reminder.html
│   │   │   │    │    └── UpdatePassword.html
│   │   │   │    ├── application.yml
│   │   │   │    └── messages.properties
```