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
