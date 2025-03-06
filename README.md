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
