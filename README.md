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

<details>
  <summary>CALLBACK, POOLING, LONG POOLING, WEBHOOKS</summary>
  <h2><strong>1. Callback (Асинхронный ответ через Webhook)</strong></h2>
<h3><strong>Описание</strong></h3>
<p class="ds-markdown-paragraph">Сервер принимает запрос, выполняет долгую операцию и уведомляет клиента через&nbsp;<strong>callback URL</strong>.</p>
<h3><strong>Пример в OpenAPI/Swagger (YAML)</strong></h3>
<div class="md-code-block md-code-block-dark">
<div class="md-code-block-banner-wrap">
<div class="md-code-block-banner md-code-block-banner-lite">
<div class="_121d384">
<div class="d2a24f03"><span class="d813de27">yaml</span></div>
<div class="d2a24f03">
<div class="efa13877">
<div class="ds-button ds-button--secondary ds-button--borderless ds-button--rect ds-button--m _7db3914" tabindex="0">
<div class="ds-button__icon">&nbsp;</div>
Copy</div>
<div class="ds-button ds-button--secondary ds-button--borderless ds-button--rect ds-button--s _7db3914" tabindex="0">
<div class="ds-button__icon">&nbsp;</div>
Download</div>
</div>
</div>
</div>
</div>
</div>
<pre><span class="token key atrule">paths</span><span class="token punctuation">:</span>
  <span class="token key atrule">/api/start-process</span><span class="token punctuation">:</span>
    <span class="token key atrule">post</span><span class="token punctuation">:</span>
      <span class="token key atrule">summary</span><span class="token punctuation">:</span> Запуск асинхронной задачи
      <span class="token key atrule">requestBody</span><span class="token punctuation">:</span>
        <span class="token key atrule">required</span><span class="token punctuation">:</span> <span class="token boolean important">true</span>
        <span class="token key atrule">content</span><span class="token punctuation">:</span>
          <span class="token key atrule">application/json</span><span class="token punctuation">:</span>
            <span class="token key atrule">schema</span><span class="token punctuation">:</span>
              <span class="token key atrule">type</span><span class="token punctuation">:</span> object
              <span class="token key atrule">properties</span><span class="token punctuation">:</span>
                <span class="token key atrule">callbackUrl</span><span class="token punctuation">:</span>
                  <span class="token key atrule">type</span><span class="token punctuation">:</span> string
                  <span class="token key atrule">format</span><span class="token punctuation">:</span> uri
                  <span class="token key atrule">example</span><span class="token punctuation">:</span> <span class="token string">"https://client.com/callback"</span>
      <span class="token key atrule">responses</span><span class="token punctuation">:</span>
        <span class="token key atrule">'202'</span><span class="token punctuation">:</span>
          <span class="token key atrule">description</span><span class="token punctuation">:</span> Задача принята в обработку</pre>
</div>
<p class="ds-markdown-paragraph"><strong>Как работает:</strong></p>
<ol start="1">
<li>
<p class="ds-markdown-paragraph">Клиент отправляет запрос с&nbsp;<code>callbackUrl</code>.</p>
</li>
<li>
<p class="ds-markdown-paragraph">Сервер отвечает&nbsp;<code>202 Accepted</code>&nbsp;и позже делает POST на&nbsp;<code>callbackUrl</code>&nbsp;с результатом.</p>
</li>
</ol>
<hr />
<h2><strong>2. Polling (Периодический опрос)</strong></h2>
<h3><strong>Описание</strong></h3>
<p class="ds-markdown-paragraph">Клиент делает запросы к серверу через фиксированные интервалы.</p>
<h3><strong>Пример в OpenAPI/Swagger (YAML)</strong></h3>
<div class="md-code-block md-code-block-dark">
<div class="md-code-block-banner-wrap">
<div class="md-code-block-banner md-code-block-banner-lite">
<div class="_121d384">
<div class="d2a24f03"><span class="d813de27">yaml</span></div>
<div class="d2a24f03">
<div class="efa13877">
<div class="ds-button ds-button--secondary ds-button--borderless ds-button--rect ds-button--m _7db3914" tabindex="0">
<div class="ds-button__icon">&nbsp;</div>
Copy</div>
<div class="ds-button ds-button--secondary ds-button--borderless ds-button--rect ds-button--s _7db3914" tabindex="0">
<div class="ds-button__icon">&nbsp;</div>
Download</div>
</div>
</div>
</div>
</div>
</div>
<pre><span class="token key atrule">paths</span><span class="token punctuation">:</span>
  /api/status/<span class="token punctuation">{</span>taskId<span class="token punctuation">}</span><span class="token punctuation">:</span>
    <span class="token key atrule">get</span><span class="token punctuation">:</span>
      <span class="token key atrule">summary</span><span class="token punctuation">:</span> Проверить статус задачи
      <span class="token key atrule">parameters</span><span class="token punctuation">:</span>
        <span class="token punctuation">-</span> <span class="token key atrule">name</span><span class="token punctuation">:</span> taskId
          <span class="token key atrule">in</span><span class="token punctuation">:</span> path
          <span class="token key atrule">required</span><span class="token punctuation">:</span> <span class="token boolean important">true</span>
          <span class="token key atrule">schema</span><span class="token punctuation">:</span>
            <span class="token key atrule">type</span><span class="token punctuation">:</span> string
      <span class="token key atrule">responses</span><span class="token punctuation">:</span>
        <span class="token key atrule">'200'</span><span class="token punctuation">:</span>
          <span class="token key atrule">description</span><span class="token punctuation">:</span> Статус задачи
          <span class="token key atrule">content</span><span class="token punctuation">:</span>
            <span class="token key atrule">application/json</span><span class="token punctuation">:</span>
              <span class="token key atrule">schema</span><span class="token punctuation">:</span>
                <span class="token key atrule">type</span><span class="token punctuation">:</span> object
                <span class="token key atrule">properties</span><span class="token punctuation">:</span>
                  <span class="token key atrule">status</span><span class="token punctuation">:</span>
                    <span class="token key atrule">type</span><span class="token punctuation">:</span> string
                    <span class="token key atrule">enum</span><span class="token punctuation">:</span> <span class="token punctuation">[</span>pending<span class="token punctuation">,</span> completed<span class="token punctuation">,</span> failed<span class="token punctuation">]</span></pre>
</div>
<p class="ds-markdown-paragraph"><strong>Как работает:</strong></p>
<ol start="1">
<li>
<p class="ds-markdown-paragraph">Клиент вызывает&nbsp;<code>/api/status/123</code>&nbsp;каждые 5 секунд.</p>
</li>
<li>
<p class="ds-markdown-paragraph">Сервер возвращает&nbsp;<code>{"status": "pending"}</code>&nbsp;или&nbsp;<code>{"status": "completed"}</code>.</p>
</li>
</ol>
<hr />
<h2><strong>3. Long Polling (Долгий опрос)</strong></h2>
<h3><strong>Описание</strong></h3>
<p class="ds-markdown-paragraph">Сервер держит соединение открытым, пока не появится результат или не истечёт таймаут.</p>
<h3><strong>Пример в OpenAPI/Swagger (YAML)</strong></h3>
<div class="md-code-block md-code-block-dark">
<div class="md-code-block-banner-wrap">
<div class="md-code-block-banner md-code-block-banner-lite">
<div class="_121d384">
<div class="d2a24f03"><span class="d813de27">yaml</span></div>
<div class="d2a24f03">
<div class="efa13877">
<div class="ds-button ds-button--secondary ds-button--borderless ds-button--rect ds-button--m _7db3914" tabindex="0">
<div class="ds-button__icon">&nbsp;</div>
Copy</div>
<div class="ds-button ds-button--secondary ds-button--borderless ds-button--rect ds-button--s _7db3914" tabindex="0">
<div class="ds-button__icon">&nbsp;</div>
Download</div>
</div>
</div>
</div>
</div>
</div>
<pre><span class="token key atrule">paths</span><span class="token punctuation">:</span>
  <span class="token key atrule">/api/wait-for-update</span><span class="token punctuation">:</span>
    <span class="token key atrule">get</span><span class="token punctuation">:</span>
      <span class="token key atrule">summary</span><span class="token punctuation">:</span> Ожидание обновления (long polling)
      <span class="token key atrule">parameters</span><span class="token punctuation">:</span>
        <span class="token punctuation">-</span> <span class="token key atrule">name</span><span class="token punctuation">:</span> timeout
          <span class="token key atrule">in</span><span class="token punctuation">:</span> query
          <span class="token key atrule">schema</span><span class="token punctuation">:</span>
            <span class="token key atrule">type</span><span class="token punctuation">:</span> integer
            <span class="token key atrule">default</span><span class="token punctuation">:</span> <span class="token number">30</span>
      <span class="token key atrule">responses</span><span class="token punctuation">:</span>
        <span class="token key atrule">'200'</span><span class="token punctuation">:</span>
          <span class="token key atrule">description</span><span class="token punctuation">:</span> Данные получены
          <span class="token key atrule">content</span><span class="token punctuation">:</span>
            <span class="token key atrule">application/json</span><span class="token punctuation">:</span>
              <span class="token key atrule">schema</span><span class="token punctuation">:</span>
                <span class="token key atrule">type</span><span class="token punctuation">:</span> object
                <span class="token key atrule">properties</span><span class="token punctuation">:</span>
                  <span class="token key atrule">update</span><span class="token punctuation">:</span>
                    <span class="token key atrule">type</span><span class="token punctuation">:</span> string
        <span class="token key atrule">'304'</span><span class="token punctuation">:</span>
          <span class="token key atrule">description</span><span class="token punctuation">:</span> Нет новых данных (таймаут)</pre>
</div>
<p class="ds-markdown-paragraph"><strong>Как работает:</strong></p>
<ol start="1">
<li>
<p class="ds-markdown-paragraph">Клиент отправляет&nbsp;<code>/api/wait-for-update?timeout=30</code>.</p>
</li>
<li>
<p class="ds-markdown-paragraph">Сервер ждёт до 30 секунд и отвечает&nbsp;<code>200 OK</code>&nbsp;при новых данных или&nbsp;<code>304 Not Modified</code>&nbsp;при таймауте.</p>
</li>
</ol>
<hr />
<h2><strong>4. Webhooks (Сервер инициирует запрос)</strong></h2>
<h3><strong>Описание</strong></h3>
<p class="ds-markdown-paragraph">Клиент регистрирует URL, на который сервер отправляет события.</p>
<h3><strong>Пример в OpenAPI/Swagger (YAML)</strong></h3>
<div class="md-code-block md-code-block-dark">
<div class="md-code-block-banner-wrap">
<div class="md-code-block-banner md-code-block-banner-lite">
<div class="_121d384">
<div class="d2a24f03"><span class="d813de27">yaml</span></div>
<div class="d2a24f03">
<div class="efa13877">
<div class="ds-button ds-button--secondary ds-button--borderless ds-button--rect ds-button--m _7db3914" tabindex="0">
<div class="ds-button__icon">&nbsp;</div>
Copy</div>
<div class="ds-button ds-button--secondary ds-button--borderless ds-button--rect ds-button--s _7db3914" tabindex="0">
<div class="ds-button__icon">&nbsp;</div>
Download</div>
</div>
</div>
</div>
</div>
</div>
<pre><span class="token key atrule">paths</span><span class="token punctuation">:</span>
  <span class="token key atrule">/webhooks</span><span class="token punctuation">:</span>
    <span class="token key atrule">post</span><span class="token punctuation">:</span>
      <span class="token key atrule">summary</span><span class="token punctuation">:</span> Регистрация вебхука
      <span class="token key atrule">requestBody</span><span class="token punctuation">:</span>
        <span class="token key atrule">required</span><span class="token punctuation">:</span> <span class="token boolean important">true</span>
        <span class="token key atrule">content</span><span class="token punctuation">:</span>
          <span class="token key atrule">application/json</span><span class="token punctuation">:</span>
            <span class="token key atrule">schema</span><span class="token punctuation">:</span>
              <span class="token key atrule">type</span><span class="token punctuation">:</span> object
              <span class="token key atrule">properties</span><span class="token punctuation">:</span>
                <span class="token key atrule">url</span><span class="token punctuation">:</span>
                  <span class="token key atrule">type</span><span class="token punctuation">:</span> string
                  <span class="token key atrule">format</span><span class="token punctuation">:</span> uri
                  <span class="token key atrule">example</span><span class="token punctuation">:</span> <span class="token string">"https://client.com/webhook"</span>
                <span class="token key atrule">events</span><span class="token punctuation">:</span>
                  <span class="token key atrule">type</span><span class="token punctuation">:</span> array
                  <span class="token key atrule">items</span><span class="token punctuation">:</span>
                    <span class="token key atrule">type</span><span class="token punctuation">:</span> string
                    <span class="token key atrule">enum</span><span class="token punctuation">:</span> <span class="token punctuation">[</span>order_created<span class="token punctuation">,</span> payment_received<span class="token punctuation">]</span>
      <span class="token key atrule">responses</span><span class="token punctuation">:</span>
        <span class="token key atrule">'201'</span><span class="token punctuation">:</span>
          <span class="token key atrule">description</span><span class="token punctuation">:</span> Вебхук зарегистрирован</pre>
</div>
<p class="ds-markdown-paragraph"><strong>Как работает:</strong></p>
<ol start="1">
<li>
<p class="ds-markdown-paragraph">Клиент регистрирует URL (например,&nbsp;<code>https://client.com/webhook</code>).</p>
</li>
<li>
<p class="ds-markdown-paragraph">При событии (например,&nbsp;<code>order_created</code>) сервер делает POST на этот URL:</p>
<div class="md-code-block md-code-block-dark">
<div class="md-code-block-banner-wrap">
<div class="md-code-block-banner md-code-block-banner-lite">
<div class="_121d384">
<div class="d2a24f03"><span class="d813de27">json</span></div>
<div class="d2a24f03">
<div class="efa13877">
<div class="ds-button ds-button--secondary ds-button--borderless ds-button--rect ds-button--m _7db3914" tabindex="0">
<div class="ds-button__icon">&nbsp;</div>
Copy</div>
<div class="ds-button ds-button--secondary ds-button--borderless ds-button--rect ds-button--s _7db3914" tabindex="0">
<div class="ds-button__icon">&nbsp;</div>
Download</div>
</div>
</div>
</div>
</div>
</div>
<pre><span class="token punctuation">{</span>
  <span class="token property">"event"</span><span class="token operator">:</span> <span class="token string">"order_created"</span><span class="token punctuation">,</span>
  <span class="token property">"data"</span><span class="token operator">:</span> <span class="token punctuation">{</span><span class="token property">"orderId"</span><span class="token operator">:</span> <span class="token string">"123"</span><span class="token punctuation">}</span>
<span class="token punctuation">}</span></pre>
</div>
</li>
</ol>
<hr />
<h2><strong>Сравнение методов</strong></h2>
<div class="markdown-table-wrapper">
<table>
<thead>
<tr>
<th>Метод</th>
<th>Пример запроса (YAML)</th>
<th>Когда использовать?</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Callback</strong></td>
<td><code>callbackUrl: "https://client.com/callback"</code></td>
<td>Долгие асинхронные операции (платежи).</td>
</tr>
<tr>
<td><strong>Polling</strong></td>
<td>GET&nbsp;<code>/api/status/{taskId}</code></td>
<td>Простые задачи с допустимой задержкой.</td>
</tr>
<tr>
<td><strong>Long Polling</strong></td>
<td>GET&nbsp;<code>/api/wait-for-update?timeout=30</code></td>
<td>Чат, уведомления в реальном времени.</td>
</tr>
<tr>
<td><strong>Webhooks</strong></td>
<td>POST&nbsp;<code>/webhooks</code>&nbsp;с&nbsp;<code>url</code>&nbsp;и&nbsp;<code>events</code></td>
<td>Мгновенные события (GitHub, Stripe).</td>
</tr>
</tbody>
</table>
</div>
<hr />
<h3><strong>Когда что выбирать?</strong></h3>
<ul>
<li>
<p class="ds-markdown-paragraph"><strong>Callback</strong>&nbsp;&rarr; Если сервер должен уведомить клиента&nbsp;<strong>однократно</strong>&nbsp;после операции.</p>
</li>
<li>
<p class="ds-markdown-paragraph"><strong>Polling</strong>&nbsp;&rarr; Если клиент может ждать и проверять статус вручную.</p>
</li>
<li>
<p class="ds-markdown-paragraph"><strong>Long Polling</strong>&nbsp;&rarr; Если нужно сократить число запросов, но WebSockets недоступны.</p>
</li>
<li>
<p class="ds-markdown-paragraph"><strong>Webhooks</strong>&nbsp;&rarr; Если сервер должен мгновенно уведомлять клиента о событиях.</p>
</li>
</ul>  
</details>

<details>
  <summary>WebSocket</summary>
  <h2>Спецификация WebSocket API для Онлайн-Аукционов</h2>
<h3>Конечные точки</h3>
<ul>
<li>WebSocket Endpoint:&nbsp;<code>ws://your-api-endpoint/auction</code></li>
</ul>
<h3>Сообщения</h3>
<h4>Сообщения от Клиента к Серверу</h4>
<ol>
<li>
<p><strong>Добавить новый предмет</strong></p>
<ul>
<li>Тип:&nbsp;<code>addItem</code></li>
<li>Полезная нагрузка:
<ul>
<li><code>id</code>: Уникальный ID</li>
<li><code>name</code>: Название предмета</li>
<li><code>startingBid</code>: Начальная ставка для аукциона</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Запустить аукцион</strong></p>
<ul>
<li>Тип:&nbsp;<code>startAuction</code></li>
<li>Полезная нагрузка:
<ul>
<li><code>id</code>: Уникальный ID предмета для аукциона</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Сделать ставку</strong></p>
<ul>
<li>Тип:&nbsp;<code>placeBid</code></li>
<li>Полезная нагрузка:
<ul>
<li><code>id</code>: Уникальный ID предмета</li>
<li><code>amount</code>: Сумма ставки</li>
<li><code>userId</code>: ID пользователя, делающего ставку</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Обновить баланс</strong></p>
<ul>
<li>Тип:&nbsp;<code>updateBalance</code></li>
<li>Полезная нагрузка:
<ul>
<li><code>userId</code>: ID пользователя</li>
<li><code>amount</code>: Новая сумма на балансе</li>
</ul>
</li>
</ul>
</li>
</ol>
<h4>Сообщения от Сервера к Клиенту</h4>
<ol>
<li>
<p><strong>Аукцион начался</strong></p>
<ul>
<li>Тип:&nbsp;<code>auctionStarted</code></li>
<li>Полезная нагрузка:
<ul>
<li><code>id</code>: Уникальный ID предмета</li>
<li><code>currentBid</code>: Текущая максимальная ставка</li>
<li><code>status</code>: "В процессе"</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Обновление ставки</strong></p>
<ul>
<li>Тип:&nbsp;<code>bidUpdate</code></li>
<li>Полезная нагрузка:
<ul>
<li><code>id</code>: Уникальный ID предмета</li>
<li><code>currentBid</code>: Новая максимальная ставка</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Аукцион завершился</strong></p>
<ul>
<li>Тип:&nbsp;<code>auctionEnded</code></li>
<li>Полезная нагрузка:
<ul>
<li><code>id</code>: Уникальный ID предмета</li>
<li><code>winnerId</code>: ID победившего пользователя</li>
<li><code>finalBid</code>: Итоговая максимальная ставка</li>
</ul>
</li>
</ul>
</li>
</ol>
<h3>Дополнительные возможности</h3>
<ul>
<li><strong>Уведомления в реальном времени</strong>: Сервер будет отправлять сообщения&nbsp;<code>bidUpdate</code>&nbsp;всем подключенным клиентам, когда будет сделана новая ставка.</li>
</ul>
<h3>Бонусные функции</h3>
<ul>
<li><strong>Автоставки</strong>: Клиенты могут отправить сообщение&nbsp;<code>setAutoBid</code>, чтобы автоматически увеличивать ставку до определенного предела.
<ul>
<li>Тип:&nbsp;<code>setAutoBid</code></li>
<li>Полезная нагрузка:
<ul>
<li><code>id</code>: Уникальный ID предмета</li>
<li><code>userId</code>: ID пользователя</li>
<li><code>limit</code>: Максимальная сумма, до которой может быть сделана автоставка</li>
</ul>
</li>
</ul>
</li>
</ul>
</details>

<details>
  <summary>Брокеры теория</summary>
  <p>&nbsp;</p>
<table border="1" cellspacing="1" cellpadding="1">
<tbody>
<tr>
<td>
<p>Параметр</p>
</td>
<td>
<p>Kafka</p>
</td>
<td>
<p>RabbitMQ</p>
</td>
</tr>
<tr>
<td>
<p>Модель взаимодействия</p>
</td>
<td>
<p>Log (журнал)</p>
</td>
<td>
<p>Очередь/издатель-подписчик</p>
</td>
</tr>
<tr>
<td>
<p>Модель взаимодействия брокера-консьюмера</p>
</td>
<td>
<p>Pull</p>
</td>
<td>
<p>Push</p>
</td>
</tr>
<tr>
<td>
<p>Поддержка паттерна запрос-ответ</p>
</td>
<td>
<p>Нет</p>
</td>
<td>
<p>Да</p>
</td>
</tr>
<tr>
<td>
<p>Паттерн масштабирования</p>
</td>
<td>
<p>Кластеризация</p>
</td>
<td>
<p>Кластеризация/федерация</p>
</td>
</tr>
<tr>
<td>
<p>Возможность записи данных (персистентность)</p>
</td>
<td>
<p>Да</p>
</td>
<td>
<p>Да</p>
</td>
</tr>
<tr>
<td>
<p>Рекомендованный размер сообщения</p>
</td>
<td>
<p>До мегабайта</p>
</td>
<td>
<p>До 100 мегабайт</p>
</td>
</tr>
<tr>
<td>
<p>Поддержка протоколов</p>
</td>
<td>
<p>Kafka Protocol/HTTP</p>
</td>
<td>
<p>AMQP/STOMP/MQTT</p>
</td>
</tr>
<tr>
<td>
<p>Пропускная способность</p>
</td>
<td>
<p>Миллион и больше сообщений в секунду</p>
</td>
<td>
<p>Десятки тысяч в секунду</p>
</td>
</tr>
</tbody>
</table>
</details>

<details>
  <summary>Apache Kafka</summary>
<h4>1. Топики Kafka</h4>
<ol>
<li><strong>Order-Confirmation</strong>: для сообщений о подтверждении заказа.</li>
<li><strong>Order-Status-Update</strong>: для сообщений о смене статуса заказа.</li>
<li><strong>Order-Cancellation</strong>: для сообщений об отмене заказа.</li>
<li><strong>Customer-Notification</strong>: для уведомлений клиентам.</li>
</ol>
<h4>2. Формат сообщений</h4>
<ul>
<li><strong>Order-Confirmation</strong>:
<ul>
<li>Key:&nbsp;<code>order_id</code></li>
<li>Value:&nbsp;<code>{ "customer_id": "XYZ", "products": [{"id": "A", "price": 10}, {"id": "B", "price": 20}], "status": "new" }</code></li>
</ul>
</li>
<li><strong>Order-Status-Update</strong>:
<ul>
<li>Key:&nbsp;<code>order_id</code></li>
<li>Value:&nbsp;<code>{ "status": "processing/shipped/cancelled" }</code></li>
</ul>
</li>
<li><strong>Order-Cancellation</strong>:
<ul>
<li>Key:&nbsp;<code>order_id</code></li>
<li>Value:&nbsp;<code>{ "reason": "customer request/stock unavailability" }</code></li>
</ul>
</li>
<li><strong>Customer-Notification</strong>:
<ul>
<li>Key:&nbsp;<code>customer_id</code></li>
<li>Value:&nbsp;<code>{ "order_id": "123", "message": "Your order is now shipped." }</code></li>
</ul>
</li>
</ul>
<h4>3. Обработка ошибок и отказоустойчивость</h4>
<ul>
<li><strong>Dead-letter queues</strong>: для сообщений, которые не удалось обработать.</li>
<li><strong>Retry policies</strong>: автоматическая попытка повторной обработки в случае временной ошибки.</li>
<li><strong>Monitoring &amp; Alerts</strong>: настроить систему мониторинга для отслеживания ошибок.</li>
</ul>
<h4>4. Хранение состояния</h4>
<ul>
<li>Хранение текущего статуса каждого заказа в базе данных для быстрого доступа.</li>
<li>Снапшоты статуса заказа для возможности восстановления.</li>
</ul>

</details>
