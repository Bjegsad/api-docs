# api-docs
my api-docs
<details>
  <summary>JRPC</summary>
  <h3>https://playground.open-rpc.org/</h3>
<h3>Основная структура</h3>
<ol>
<li><strong>openrpc</strong>: Указывает версию OpenRPC, которую следует использовать.</li>
<li><strong>info</strong>: Содержит метаинформацию о данной API-спецификации.
<ul>
<li><strong>version</strong>: Версия API.</li>
<li><strong>title</strong>: Название API.</li>
</ul>
</li>
<li><strong>servers</strong>: Список серверов, на которых работает API.
<ul>
<li><strong>name</strong>: Имя сервера.</li>
<li><strong>url</strong>: URL сервера, может содержать переменные.</li>
<li><strong>variables</strong>: Определение переменных, используемых в URL.
<ul>
<li><strong>version</strong>: Переменная для версионирования API, может быть "v1" или "v2".</li>
</ul>
</li>
</ul>
</li>
</ol>
<h3>Методы</h3>
<ol>
<li><strong>methods</strong>: Описание всех методов, которые API поддерживает.
<ul>
<li><strong>name</strong>: Имя метода.</li>
<li><strong>summary</strong>: Краткое описание метода.</li>
<li><strong>description</strong>: Подробное описание метода.</li>
</ul>
</li>
</ol>
<h4>Параметры метода</h4>
<ol>
<li><strong>params</strong>: Описание параметров, которые принимает метод.
<ul>
<li><strong>name</strong>: Имя параметра.</li>
<li><strong>description</strong>: Описание параметра.</li>
<li><strong>schema</strong>: Схема данных параметра (тип данных, возможные значения и т. д.).</li>
</ul>
</li>
</ol>
<h4>Результат метода</h4>
<ol>
<li><strong>result</strong>: Описание возможного результата выполнения метода.
<ul>
<li><strong>name</strong>: Имя результата.</li>
<li><strong>description</strong>: Описание результата.</li>
<li><strong>schema</strong>: Схема данных результата (тип данных, свойства и т. д.).</li>
</ul>
</li>
</ol>
<h4>Ошибки</h4>
<ol>
<li><strong>errors</strong>: Описание возможных ошибок, которые может вернуть метод.
<ul>
<li><strong>name</strong>: Имя ошибки.</li>
<li><strong>code</strong>: Код ошибки.</li>
<li><strong>message</strong>: Описание ошибки.</li>
<li><strong>data</strong>: Тип данных, которые могут быть приложены к ошибке.</li>
</ul>
</li>
</ol>
<h4>Примеры</h4>
<ol>
<li><strong>examples</strong>: Примеры использования метода.
<ul>
<li><strong>name</strong>: Имя примера.</li>
<li><strong>params</strong>: Используемые параметры в примере.</li>
<li><strong>result</strong>: Ожидаемый результат в примере.</li>
</ul>
</li>
</ol>
</details>

<details>
  <summary>SOAP</summary>
<h3>Объявления пространства имен и общие атрибуты</h3>
<ol>
<li>
<p><code>&lt;?xml version="1.0" encoding="UTF-8"?&gt;</code>: Эта строка объявляет версию XML и кодировку документа.</p>
</li>
<li>
<p><code>&lt;wsdl:definitions ... &gt;</code>: Этот элемент является корневым элементом для WSDL. Он объявляет все пространства имен и атрибуты, которые будут использоваться в этом WSDL документе.</p>
<ul>
<li><code>xmlns:soap</code>: Объявляет пространство имен для SOAP. Стандартный URL<span>&nbsp;</span><code>http://schemas.xmlsoap.org/wsdl/soap/</code><span>&nbsp;</span>используется для обозначения версии SOAP 1.1.</li>
<li><code>xmlns:tns</code>: Пространство имен для нашей конкретной службы. Здесь<span>&nbsp;</span><code>tns</code><span>&nbsp;</span>обозначает "Target Namespace".</li>
<li><code>xmlns:wsdl</code>: Стандартное пространство имен для WSDL.</li>
<li><code>xmlns:xsd</code>: Стандартное пространство имен для XML Schema.</li>
<li><code>targetNamespace</code>: Обозначает URL, который уникально идентифицирует наш веб-сервис.</li>
</ul>
</li>
</ol>
<h3>Определения типов</h3>
<ol>
<li>
<p><code>&lt;wsdl:types&gt;</code>: Элемент, который содержит определения всех типов данных, используемых в веб-сервисе.</p>
</li>
<li>
<p><code>&lt;xsd:schema targetNamespace="http://www.example.com/taskmanagement"&gt;</code>: Этот элемент определяет схему и использует то же пространство имен, что и весь веб-сервис.</p>
</li>
<li>
<p><code>&lt;xsd:element name="Task"&gt; ... &lt;/xsd:element&gt;</code>: Определяет структуру "Task", которая будет использована в сообщениях.</p>
</li>
</ol>
<h3>Определения сообщений</h3>
<ol>
<li><code>&lt;wsdl:message name="CreateTaskRequest"&gt; ... &lt;/wsdl:message&gt;</code>: Этот элемент определяет структуру входящего сообщения для операции<span>&nbsp;</span><code>CreateTask</code>.</li>
</ol>
<h3>Определения порта</h3>
<ol>
<li><code>&lt;wsdl:portType name="TaskManagementPortType"&gt; ... &lt;/wsdl:portType&gt;</code>: Элемент<span>&nbsp;</span><code>portType</code><span>&nbsp;</span>определяет набор операций, которые можно выполнить с веб-сервисом.</li>
</ol>
<h3>Определения привязки</h3>
<ol>
<li>
<p><code>&lt;wsdl:binding name="TaskManagementBinding" type="tns:TaskManagementPortType"&gt; ... &lt;/wsdl:binding&gt;</code>: Элемент<span>&nbsp;</span><code>binding</code><span>&nbsp;</span>описывает конкретные протоколы и форматы данных для операций и сообщений, определенных в<span>&nbsp;</span><code>portType</code>.</p>
</li>
<li>
<p><code>&lt;soap:binding style="document" transport="http://schemas.xmlsoap.org/soap/http"/&gt;</code>: Этот элемент уточняет, что используется стиль "document" и протокол "HTTP".</p>
</li>
</ol>
<h3>Определения службы</h3>
<ol>
<li>
<p><code>&lt;wsdl:service name="TaskManagementService"&gt; ... &lt;/wsdl:service&gt;</code>: Этот элемент определяет сервис и указывает порт (или порты), который будет использоваться.</p>
</li>
<li>
<p><code>&lt;soap:address location="http://www.example.com/taskmanagement"/&gt;</code>: Этот элемент определяет URL, по которому доступен веб-сервис.</p>
</li>
</ol>
</details>

<details>
  <summary>GRAPHQL</summary>
<p>playground -&nbsp;https://graphql.org/learn/queries/</p>
<p>Пример:</p>
<p>type Student {<br />id: ID!<br />name: String!<br />surname: String!<br />age: Int!<br />courseList: [Course!]!<br /><br />}<br />type Course {<br />id: ID!<br />name: String!<br />description: String!<br />cost: Int!<br />registrateStudentsCount: Int!<br />}<br />type Query {<br />students(offset: Int, limit: Int): [Student!]<br />courses(costFilter: Int!): [Course!]<br />courseById(id: ID!): Course<br />studentById(id: ID!): Student<br />}<br />type Mutation {<br />addStudent(name: String!, surname: String!, age: Int!): Student!<br />updateStudent(name: String!, surname: String!, age: Int!): Student!<br />deleteStudent(id: ID!): Boolean!<br />addCourse(name: String!, description: String!, cost: Int!): Course!<br />updateCourse(name: String!, description: String!, cost: Int!): Course!<br />deleteCourse(id: ID!): Boolean!<br />registrateStudent(studentId: ID!, courseId: ID!): Student!<br />unregistrateStudent(studentId: ID!, courseId: ID!): Student!<br />}</p>
</details>

<details>
  <summary>GRPC</summary>
<p>📌 Шпаргалка по gRPC PROTO с разными типами данных и CRUD-операциями</p>
<p>Этот пример демонстрирует работу с сущностью Product (товар) и включает:</p>
<p>&bull; Create (Создание)<br /> &bull; Read (Чтение)<br /> &bull; Update (Обновление)<br /> &bull; Delete (Удаление)<br /> &bull; List (Список товаров)<br /> &bull; Streaming (Реальное обновление)<br /> &bull; Разные типы данных (строки, числа, bool, enum, массивы, timestamps).</p>
<p>📌 1. Полный .proto файл с CRUD и документацией</p>
<p>// Файл: product_service.proto<br />// gRPC-сервис для управления товарами.<br />syntax = "proto3";</p>
<p>package product;</p>
<p>import "google/protobuf/timestamp.proto";<br />import "google/protobuf/empty.proto";</p>
<p>// 💾 Сервис управления товарами.<br />service ProductService {<br /> // 🆕 Создать новый товар.<br /> rpc CreateProduct (CreateProductRequest) returns (ProductResponse);<br /> <br /> // 🔍 Получить товар по ID.<br /> rpc GetProduct (GetProductRequest) returns (ProductResponse);<br /> <br /> // 📝 Обновить существующий товар.<br /> rpc UpdateProduct (UpdateProductRequest) returns (ProductResponse);<br /> <br /> // ❌ Удалить товар по ID.<br /> rpc DeleteProduct (DeleteProductRequest) returns (google.protobuf.Empty);<br /> <br /> // 📋 Получить список всех товаров.<br /> rpc ListProducts (ListProductsRequest) returns (ListProductsResponse);<br /> <br /> // 📡 Реальный стриминг обновлений товаров.<br /> rpc StreamProductUpdates (google.protobuf.Empty) returns (stream ProductResponse);<br />}</p>
<p>// 🏷️ Структура товара.<br />message Product {<br /> // Уникальный ID товара (UUID).<br /> string id = 1;<br /> <br /> // Название товара.<br /> string name = 2;<br /> <br /> // Описание товара.<br /> string description = 3;<br /> <br /> // Цена товара в центах (например, 1999 = $19.99).<br /> uint32 price = 4;<br /> <br /> // Категория товара.<br /> Category category = 5;<br /> <br /> // В наличии ли товар.<br /> bool in_stock = 6;<br /> <br /> // Дата создания.<br /> google.protobuf.Timestamp created_at = 7;<br /> <br /> // Список тегов (например, ["electronics", "sale"]).<br /> repeated string tags = 8;<br />}</p>
<p>// 🔖 Категории товаров.<br />enum Category {<br /> CATEGORY_UNSPECIFIED = 0; // Не указано.<br /> ELECTRONICS = 1; // Электроника.<br /> CLOTHING = 2; // Одежда.<br /> FOOD = 3; // Продукты питания.<br />}</p>
<p>// 📌 Запрос на создание товара.<br />message CreateProductRequest {<br /> // Название товара.<br /> string name = 1;<br /> <br /> // Описание товара.<br /> string description = 2;<br /> <br /> // Цена товара.<br /> uint32 price = 3;<br /> <br /> // Категория.<br /> Category category = 4;<br /> <br /> // В наличии ли товар.<br /> bool in_stock = 5;<br /> <br /> // Теги.<br /> repeated string tags = 6;<br />}</p>
<p>// 📌 Запрос на получение товара.<br />message GetProductRequest {<br /> // ID товара.<br /> string product_id = 1;<br />}</p>
<p>// 📌 Запрос на обновление товара.<br />message UpdateProductRequest {<br /> // ID товара.<br /> string product_id = 1;<br /> <br /> // Новое название (опционально).<br /> optional string name = 2;<br /> <br /> // Новое описание (опционально).<br /> optional string description = 3;<br /> <br /> // Новая цена (опционально).<br /> optional uint32 price = 4;<br /> <br /> // Новая категория (опционально).<br /> optional Category category = 5;<br /> <br /> // В наличии ли товар (опционально).<br /> optional bool in_stock = 6;<br /> <br /> // Новые теги (опционально).<br /> repeated string tags = 7;<br />}</p>
<p>// 📌 Запрос на удаление товара.<br />message DeleteProductRequest {<br /> // ID товара.<br /> string product_id = 1;<br />}</p>
<p>// 📌 Запрос на список товаров.<br />message ListProductsRequest {<br /> // Фильтр по категории (опционально).<br /> optional Category category = 1;<br /> <br /> // Фильтр по наличию (опционально).<br /> optional bool in_stock = 2;<br />}</p>
<p>// 📌 Ответ со списком товаров.<br />message ListProductsResponse {<br /> // Список товаров.<br /> repeated Product products = 1;<br />}</p>
<p>// 📌 Ответ с данными о товаре.<br />message ProductResponse {<br /> // Данные о товаре.<br /> Product product = 1;<br />}</p>
<p>&nbsp;</p>
<p>&bull; string &mdash; name, description, tags, id<br /> &bull; uint32 &mdash; price (цена в центах)<br /> &bull; bool &mdash; in_stock (наличие товара)<br /> &bull; enum &mdash; category (категория товара)<br /> &bull; repeated &mdash; tags (список тегов)<br /> &bull; google.protobuf.Timestamp &mdash; created_at (дата создания)<br /> &bull; optional &mdash; UpdateProductRequest, чтобы сделать поля необязательными</p>
</details>


<details>
  <summary>REST</summary>
  ![image](https://github.com/user-attachments/assets/da29e760-66d1-479c-94d3-f9f127e13feb)

</details>
