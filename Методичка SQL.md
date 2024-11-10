---


---

<h1 id="mysql.-методологические-указания.">MySQL. Методологические указания.</h1>
<p>Романенко Е.О. // НИТУ МИСИС</p>
<h1 id="теория">Теория</h1>
<h2 id="что-такое-sql">Что такое SQL</h2>
<blockquote>
<p><strong>SQL (Structured Query Language // Язык Структурированных Запросов)</strong> —<br>
это язык программирования, предназначенный для управления и обработки<br>
данных в реляционных базах данных.</p>
</blockquote>
<h2 id="преимущества">Преимущества</h2>
<p>Преимущества SQL относительно стандартных решений обработки данных заключаются в том, что SQL позволяет обращаться к данным единым запросом, обладает реляционностью и высокой скоростью, благодарю скомпилированным запросам, строгой типизации и продвинутыми алгоритмами поиска и сортировки.</p>
<h1 id="типы-данных-в-mysql">Типы данных в MySQL</h1>
<p>В MySQL типы данных разделены на основные группы:</p>
<ol>
<li><strong>Числовые типы</strong> (<code>Numeric</code>)</li>
<li><strong>Дата и время</strong> (<code>Date and Time</code>)</li>
<li><strong>Строковые типы</strong> (<code>String</code>)</li>
<li><strong>Логические типы</strong> (<code>Boolean</code>)</li>
</ol>
<h2 id="числовые-типы-данных">Числовые типы данных</h2>
<h3 id="целочисленные-типы">Целочисленные типы</h3>

<table>
<thead>
<tr>
<th>Тип</th>
<th>Размер</th>
<th>Диапазон со знаком</th>
<th>Диапазон без знака</th>
<th>Область применения</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>TINYINT</code></td>
<td>1 байт</td>
<td>-128 до 127</td>
<td>0 до 255</td>
<td>Для небольших чисел, таких как индикаторы состояний.</td>
</tr>
<tr>
<td><code>SMALLINT</code></td>
<td>2 байта</td>
<td>-32768 до 32767</td>
<td>0 до 65535</td>
<td>Подходит для небольших числовых данных, таких как года.</td>
</tr>
<tr>
<td><code>MEDIUMINT</code></td>
<td>3 байта</td>
<td>-8388608 до 8388607</td>
<td>0 до 16777215</td>
<td>Используется, когда требуется большее, но не слишком большое число.</td>
</tr>
<tr>
<td><code>INT</code></td>
<td>4 байта</td>
<td>-2147483648 до 2147483647</td>
<td>0 до 4294967295</td>
<td>Подходит для целых чисел средней величины.</td>
</tr>
<tr>
<td><code>BIGINT</code></td>
<td>8 байт</td>
<td>-9223372036854775808 до 9223372036854775807</td>
<td>0 до 18446744073709551615</td>
<td>Для очень больших чисел, таких как уникальные идентификаторы.</td>
</tr>
</tbody>
</table><p>Примечания:</p>
<ul>
<li><strong>Со знаком</strong>: позволяет использовать отрицательные и положительные числа.</li>
<li><strong>Без знака</strong>: только положительные числа.</li>
</ul>
<h3 id="дробные-типы-числа-с-плавающей-точкой">Дробные типы (Числа с плавающей точкой)</h3>

<table>
<thead>
<tr>
<th>Тип</th>
<th>Размер</th>
<th>Диапазон</th>
<th>Область применения</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>FLOAT</code></td>
<td>4 байта</td>
<td>~3.402823466E+38 до ~1.175494351E-38</td>
<td>Для чисел с небольшой точностью.</td>
</tr>
<tr>
<td><code>DOUBLE</code></td>
<td>8 байт</td>
<td>~1.7976931348623157E+308 до ~2.2250738585072014E-308</td>
<td>Для чисел с большей точностью.</td>
</tr>
<tr>
<td><code>DECIMAL(M,D)</code></td>
<td>Зависит от M</td>
<td>Задает точное значение с количеством цифр <code>M</code> и дробной частью <code>D</code>.</td>
<td>Для финансовых данных, где требуется высокая точность.</td>
</tr>
</tbody>
</table><h2 id="дата-и-время">Дата и время</h2>

<table>
<thead>
<tr>
<th>Тип</th>
<th>Формат</th>
<th>Диапазон</th>
<th>Область применения</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>DATE</code></td>
<td><code>YYYY-MM-DD</code></td>
<td>1000-01-01 до 9999-12-31</td>
<td>Для хранения даты без времени.</td>
</tr>
<tr>
<td><code>TIME</code></td>
<td><code>HH:MM:SS</code></td>
<td>-838:59:59 до 838:59:59</td>
<td>Для хранения интервалов времени.</td>
</tr>
<tr>
<td><code>DATETIME</code></td>
<td><code>YYYY-MM-DD HH:MM:SS</code></td>
<td>1000-01-01 00:00:00 до 9999-12-31 23:59:59</td>
<td>Для хранения даты и времени.</td>
</tr>
<tr>
<td><code>TIMESTAMP</code></td>
<td><code>YYYY-MM-DD HH:MM:SS</code></td>
<td>1970-01-01 00:00:01 UTC до 2038-01-19 03:14:07 UTC</td>
<td>Автоматически обновляется при изменении записи.</td>
</tr>
<tr>
<td><code>YEAR</code></td>
<td><code>YYYY</code></td>
<td>1901 до 2155</td>
<td>Для хранения годов.</td>
</tr>
</tbody>
</table><p><strong>Примечания:</strong></p>
<ul>
<li><strong><code>DATETIME</code></strong>: Не зависит от временной зоны, подходит для фиксированных временных данных.</li>
<li><strong><code>TIMESTAMP</code></strong>: Зависит от временной зоны, используется для временных отметок и логов.</li>
</ul>
<h2 id="строковые-типы-данных">Строковые типы данных</h2>
<h3 id="символьные-и-текстовые-типы">Символьные и текстовые типы</h3>

<table>
<thead>
<tr>
<th>Тип</th>
<th>Максимальный размер</th>
<th>Область применения</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>CHAR(M)</code></td>
<td><code>M</code> символов, до 255</td>
<td>Для строк фиксированной длины, например, кодов стран.</td>
</tr>
<tr>
<td><code>VARCHAR(M)</code></td>
<td><code>M</code> символов, до 65535</td>
<td>Для строк переменной длины. Например, имена или адреса.</td>
</tr>
<tr>
<td><code>TINYTEXT</code></td>
<td>255 байт</td>
<td>Для небольших текстовых данных.</td>
</tr>
<tr>
<td><code>TEXT</code></td>
<td>65535 байт</td>
<td>Для хранения средних текстовых данных.</td>
</tr>
<tr>
<td><code>MEDIUMTEXT</code></td>
<td>16,777,215 байт</td>
<td>Подходит для больших объемов текста, например, описаний.</td>
</tr>
<tr>
<td><code>LONGTEXT</code></td>
<td>4,294,967,295 байт</td>
<td>Для хранения очень больших объемов текста, таких как документы.</td>
</tr>
</tbody>
</table><h3 id="двоичные-типы">Двоичные типы</h3>

<table>
<thead>
<tr>
<th>Тип</th>
<th>Максимальный размер</th>
<th>Область применения</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>BINARY(M)</code></td>
<td><code>M</code> байт, до 255</td>
<td>Для хранения данных фиксированной длины, например, хешей.</td>
</tr>
<tr>
<td><code>VARBINARY(M)</code></td>
<td><code>M</code> байт, до 65535</td>
<td>Для двоичных данных переменной длины.</td>
</tr>
<tr>
<td><code>TINYBLOB</code></td>
<td>255 байт</td>
<td>Для небольших двоичных данных.</td>
</tr>
<tr>
<td><code>BLOB</code></td>
<td>65535 байт</td>
<td>Хранит двоичные данные среднего объема, например, изображения.</td>
</tr>
<tr>
<td><code>MEDIUMBLOB</code></td>
<td>16,777,215 байт</td>
<td>Для больших файлов, таких как видео.</td>
</tr>
<tr>
<td><code>LONGBLOB</code></td>
<td>4,294,967,295 байт</td>
<td>Для хранения очень больших файлов.</td>
</tr>
</tbody>
</table><h2 id="логические-типы-данных">Логические типы данных</h2>

<table>
<thead>
<tr>
<th>Тип</th>
<th>Представление</th>
<th>Область применения</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>BOOLEAN</code> или <code>BOOL</code></td>
<td>Хранится как <code>TINYINT(1)</code> (0 = <code>false</code>, 1 = <code>true</code>)</td>
<td>Используется для хранения логических значений, например, флагов состояния.</td>
</tr>
</tbody>
</table><p><strong>Примечание:</strong></p>
<ul>
<li>В MySQL логический тип <code>BOOLEAN</code> является псевдонимом для <code>TINYINT(1)</code>. Значение <code>0</code> интерпретируется как <code>false</code>, а любое ненулевое значение как <code>true</code>. Часто используется для флагов и других двоичных состояний.</li>
</ul>
<h2 id="прочие-типы-данных">Прочие типы данных</h2>

<table>
<thead>
<tr>
<th>Тип</th>
<th>Описание</th>
<th>Область применения</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>ENUM</code></td>
<td>Список значений, например: <code>ENUM('small', 'medium', 'large')</code></td>
<td>Для хранения предопределенных списков, например, категорий.</td>
</tr>
<tr>
<td><code>SET</code></td>
<td>Множество значений, например: <code>SET('a', 'b', 'c')</code></td>
<td>Для хранения нескольких предопределенных значений одновременно.</td>
</tr>
</tbody>
</table><h3 id="ограничения-и-рекомендации">Ограничения и рекомендации</h3>
<ul>
<li><strong>Размер и диапазон</strong>: Выбор слишком большого типа данных может занимать много памяти и увеличивать время обработки, поэтому выбирайте минимально необходимые размеры.</li>
<li><strong>Типы <code>BLOB</code> и <code>TEXT</code></strong>: Эти типы данных имеют большие ограничения на объем хранимых данных, что может вызвать проблемы с производительностью при использовании их в больших объемах.</li>
<li><strong>Типы данных для даты и времени</strong>: Используйте <code>TIMESTAMP</code>, если важна временная метка с учетом временной зоны. Для постоянных дат лучше подойдет <code>DATETIME</code>.</li>
</ul>
<h1 id="ограничители-в-sql">Ограничители в SQL</h1>
<blockquote>
<p><strong>Ограничители (constraints) в MySQL</strong> — помогают обеспечивать целостность<br>
данных и устанавливают правила, которым значения в таблице должны<br>
соответствовать.</p>
</blockquote>
<h2 id="основные-типы-ограничителей">Основные типы ограничителей</h2>
<h3 id="primary-key"><code>PRIMARY KEY</code></h3>
<p>Ограничитель <code>PRIMARY KEY</code> уникально идентифицирует каждую запись в таблице и объединяет свойства <code>UNIQUE</code> и <code>NOT NULL</code>. Таблица может иметь только один первичный ключ, который может состоять из одного или нескольких столбцов.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    username <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">50</span><span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>Альтернативная запись:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    username <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">50</span><span class="token punctuation">)</span>
    <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">(</span>id<span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="not-null"><code>NOT NULL</code></h3>
<p>Ограничитель <code>NOT NULL</code> не позволяет столбцу принимать значение <code>NULL</code>. Это означает, что поле всегда должно содержать данные, и вставка или обновление записи без значения в этом поле вызовет ошибку.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span><span class="token punctuation">,</span>
    username <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">50</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="unique"><code>UNIQUE</code></h3>
<p>Ограничитель <code>UNIQUE</code> обеспечивает уникальность значений в одном или нескольких столбцах, предотвращая дублирование данных. Можно задать <code>UNIQUE</code> на один столбец или комбинацию нескольких столбцов для уникальности по ним.</p>
<p>Для одного столбца</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    email <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">255</span><span class="token punctuation">)</span> <span class="token keyword">UNIQUE</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>Для нескольких столбцов</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    first_name <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">50</span><span class="token punctuation">)</span><span class="token punctuation">,</span>
    last_name <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">50</span><span class="token punctuation">)</span><span class="token punctuation">,</span>
    <span class="token keyword">UNIQUE</span> <span class="token punctuation">(</span>first_name<span class="token punctuation">,</span> last_name<span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="композитные-ключи-составные-primary-key-и-unique">Композитные ключи (составные <code>PRIMARY KEY</code> и <code>UNIQUE</code>)</h3>
<p>Композитный (или составной) ключ используется для уникальности комбинации значений двух или более столбцов. Композитный <code>PRIMARY KEY</code> действует как уникальный идентификатор на уровне всей комбинации значений. Является обязательный условием реализации внешней связи Many-to-Many.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> orders <span class="token punctuation">(</span>
    order_id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    product_id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span> <span class="token punctuation">(</span>order_id<span class="token punctuation">,</span> product_id<span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="foreign-key"><code>FOREIGN KEY</code></h3>
<p>Ограничитель <code>FOREIGN KEY</code> создает связь между таблицами и обеспечивает целостность данных, ограничивая возможные значения ссылками на первичный ключ другой таблицы. Этот тип ограничителя особенно полезен при работе с реляционными данными.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> orders <span class="token punctuation">(</span>
    order_id <span class="token keyword">INT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    user_id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    <span class="token keyword">FOREIGN</span> <span class="token keyword">KEY</span> <span class="token punctuation">(</span>user_id<span class="token punctuation">)</span> <span class="token keyword">REFERENCES</span> users<span class="token punctuation">(</span>id<span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><code>FOREIGN KEY</code> также поддерживает действия <code>ON DELETE</code> и <code>ON UPDATE</code>, такие как <code>CASCADE</code>, что позволяет автоматически удалять или обновлять связанные записи при изменении данных в таблице-родителе.</p>
<h3 id="check"><code>CHECK</code></h3>
<p>Ограничитель <code>CHECK</code> позволяет задавать условие, которому должны соответствовать значения в столбце. Например, <code>CHECK</code> может ограничить диапазон значений или задать конкретные допустимые значения.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> products <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    price <span class="token keyword">DECIMAL</span><span class="token punctuation">(</span><span class="token number">10</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span> <span class="token keyword">CHECK</span> <span class="token punctuation">(</span>price <span class="token operator">&gt;=</span> <span class="token number">0</span><span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="default"><code>DEFAULT</code></h3>
<p>Ограничитель <code>DEFAULT</code> определяет значение по умолчанию для столбца, если при вставке записи значение в этом столбце не указано. Это позволяет упростить структуру записей, когда одно и то же значение применяется часто.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    is_active <span class="token keyword">TINYINT</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span> <span class="token keyword">DEFAULT</span> <span class="token number">1</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="auto_increment"><code>AUTO_INCREMENT</code></h3>
<p>Ограничитель <code>AUTO_INCREMENT</code> автоматически увеличивает значение столбца для каждой новой записи. Чаще всего используется для создания уникальных идентификаторов (ID).</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span> <span class="token keyword">AUTO_INCREMENT</span><span class="token punctuation">,</span>
    username <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">50</span><span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h3 id="unsigned"><code>UNSIGNED</code></h3>
<p>Ограничитель <code>UNSIGNED</code> применяется к числовым столбцам и запрещает использование отрицательных значений или же принудительно заставляет все записанные в колонку значения быть больше 0. Это позволяет увеличить количество допустимых значений, потому что нет необходимости хранить информацию о том, каким знаком обладает число (+ или -), так как он всегда +. <code>UNSIGNED</code> полезен, когда необходимо увеличить максимальный диапазон положительных чисел в столбце.</p>
<pre class=" language-sql"><code class="prism  language-sql"> <span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> products <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span> UNSIGNED <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    quantity <span class="token keyword">INT</span> UNSIGNED
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="рекомендации-по-использованию-ограничителей">Рекомендации по использованию ограничителей</h2>
<ul>
<li><strong><code>PRIMARY KEY</code></strong>: Используйте для уникального идентификатора каждой записи в таблице, особенно если данные связаны с другими таблицами через <code>FOREIGN KEY</code>.</li>
<li><strong><code>NOT NULL</code></strong>: Применяйте для полей, которые всегда должны иметь значение, чтобы избежать <code>NULL</code>, если это требуется бизнес-логикой.</li>
<li><strong><code>UNIQUE</code></strong>: Используйте для полей, значения которых должны быть уникальными (например, email, username).</li>
<li><strong><code>FOREIGN KEY</code></strong>: Поддерживает целостность данных между таблицами, особенно для связанных сущностей.</li>
<li><strong>Комбинирование ограничителей</strong>: Например, <code>DEFAULT</code> и <code>NOT NULL</code> можно использовать для полей с предсказуемым значением по умолчанию.</li>
<li><strong><code>AUTO_INCREMENT</code></strong>: Удобен для автоматического создания уникальных числовых значений, особенно для первичных ключей.</li>
<li><strong><code>CHECK</code></strong>: Задавайте ограничения по диапазону значений для простых валидаций.</li>
</ul>
<h1 id="создание-таблицы-c-create-table">Создание таблицы c <code>CREATE TABLE</code></h1>
<p><code>CREATE TABLE</code> используется для создания таблиц. В команде указываются название таблицы, названия и типы данных столбцов, а также дополнительные ограничения.</p>
<p>Пример:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    user_id <span class="token keyword">INT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    username <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">50</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span><span class="token punctuation">,</span>
    email <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">100</span><span class="token punctuation">)</span> <span class="token keyword">UNIQUE</span><span class="token punctuation">,</span>
    created_at <span class="token keyword">TIMESTAMP</span> <span class="token keyword">DEFAULT</span> <span class="token keyword">CURRENT_TIMESTAMP</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>В этом примере создается таблица <code>users</code> с полями:</p>
<ul>
<li><code>user_id</code>: целочисленный идентификатор (первичный ключ).</li>
<li><code>username</code>: строка длиной до 50 символов, не может быть пустой.</li>
<li><code>email</code>: строка длиной до 100 символов, уникальная.</li>
<li><code>created_at</code>: поле типа <code>TIMESTAMP</code>, по умолчанию сохраняющее текущую дату и время.</li>
</ul>
<h1 id="администрирование-таблицы-c-alter-table">Администрирование таблицы c <code>ALTER TABLE</code></h1>
<h2 id="определение">Определение</h2>
<blockquote>
<p><strong><code>ALTER TABLE</code></strong> — используется для изменения структуры существующей таблицы в MySQL. С помощью <code>ALTER TABLE</code> можно добавлять, удалять или<br>
изменять столбцы, устанавливать или удалять ограничения, а также<br>
выполнять другие операции, меняющие структуру таблицы без<br>
необходимости её удаления и повторного создания.</p>
</blockquote>
<h2 id="добавление-столбцов-add-column">Добавление столбцов (<code>ADD COLUMN</code>)</h2>
<p>Чтобы добавить новый столбец в таблицу, используйте <code>ADD COLUMN</code>. Новый столбец добавляется в конец таблицы, если не указано иное.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> table_name 
<span class="token keyword">ADD</span> <span class="token keyword">COLUMN</span> column_name column_type <span class="token punctuation">[</span>позиция<span class="token punctuation">]</span><span class="token punctuation">;</span>
</code></pre>
<p>Если нужно разместить столбец в определённой позиции, можно использовать ключевые слова <code>FIRST</code> или <code>AFTER column_name</code>.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> users
<span class="token keyword">ADD</span> <span class="token keyword">COLUMN</span> middle_name <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">50</span><span class="token punctuation">)</span> <span class="token keyword">AFTER</span> first_name<span class="token punctuation">;</span>
</code></pre>
<h2 id="удаление-столбцов-drop-column">Удаление столбцов (<code>DROP COLUMN</code>)</h2>
<p>Для удаления существующего столбца из таблицы используйте <code>DROP COLUMN</code>.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> table_name
<span class="token keyword">DROP</span> <span class="token keyword">COLUMN</span> column_name<span class="token punctuation">;</span>
</code></pre>
<h2 id="изменение-типа-столбца-modify-column-и-change-column">Изменение типа столбца (<code>MODIFY COLUMN</code> и <code>CHANGE COLUMN</code>)</h2>
<p>Команда <code>MODIFY COLUMN</code> позволяет изменить тип данных и другие свойства существующего столбца.</p>
<p>Синтаксис:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> table_name
<span class="token keyword">MODIFY</span> <span class="token keyword">COLUMN</span> column_name new_column_type<span class="token punctuation">;</span>
</code></pre>
<p>Пример:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> users
<span class="token keyword">MODIFY</span> <span class="token keyword">COLUMN</span> age <span class="token keyword">TINYINT</span> UNSIGNED<span class="token punctuation">;</span>
</code></pre>
<p>Команда <code>CHANGE COLUMN</code> используется для изменения имени и типа столбца одновременно.</p>
<p>Cинтаксис:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> table_name
CHANGE <span class="token keyword">COLUMN</span> old_column_name new_column_name new_column_type<span class="token punctuation">;</span>
</code></pre>
<p>Пример:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> users
CHANGE <span class="token keyword">COLUMN</span> age user_age <span class="token keyword">SMALLINT</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="переименование-таблицы-rename-to">Переименование таблицы (<code>RENAME TO</code>)</h2>
<p>Для изменения имени таблицы используйте <code>RENAME TO</code>.</p>
<p>Cинтаксис:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> table_name
<span class="token keyword">RENAME</span> <span class="token keyword">TO</span> new_table_name<span class="token punctuation">;</span>
</code></pre>
<p>Пример:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> users 
<span class="token keyword">RENAME</span> <span class="token keyword">TO</span> app_users<span class="token punctuation">;</span>
</code></pre>
<h2 id="переименование-столбца-rename-column-to">Переименование столбца (<code>RENAME COLUMN TO</code>)</h2>
<p>Для изменения имени колонки можно использовать <code>RENAME COLUMN ... TO</code></p>
<p>Cинтаксис:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> table_name
<span class="token keyword">RENAME</span> <span class="token keyword">COLUMN</span> old_column <span class="token keyword">TO</span> new_column<span class="token punctuation">;</span>
</code></pre>
<p>Пример:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">ALTER</span> <span class="token keyword">TABLE</span> users
<span class="token keyword">RENAME</span> <span class="token keyword">COLUMN</span> age <span class="token keyword">TO</span> user_age<span class="token punctuation">;</span>
</code></pre>
<h1 id="представления-view-s">Представления (<code>VIEW-s</code>)</h1>
<h2 id="определение-1">Определение</h2>
<blockquote>
<p><strong>VIEW</strong> (представление) — это виртуальная таблица в базе данных, которая формируется из результата выполнения SQL-запроса или же<br>
заготовленный фильтр уже существующих данных. Представление может<br>
включать данные из одной или нескольких таблиц. Оно предоставляет<br>
доступ к данным без необходимости их дублирования и облегчает работу с<br>
ними, так как вы можете выполнять запросы к представлению как к<br>
обычной таблице.</p>
</blockquote>
<h2 id="создание-представления">Создание представления</h2>
<p>Для создания представления используется оператор <code>CREATE VIEW</code>.</p>
<p>Cинтаксис:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">VIEW</span> имя_представления <span class="token keyword">AS</span>
<span class="token keyword">SELECT</span> столбцы
<span class="token keyword">FROM</span> таблицы
<span class="token keyword">WHERE</span> условия<span class="token punctuation">;</span>
</code></pre>
<p>Пример:</p>
<p>Предположим, у нас есть таблица <code>employees</code>, и мы хотим создать представление, которое покажет только сотрудников, работающих в отделе <code>Sales</code>:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">VIEW</span> sales_employees <span class="token keyword">AS</span>
<span class="token keyword">SELECT</span> employee_id<span class="token punctuation">,</span> first_name<span class="token punctuation">,</span> last_name<span class="token punctuation">,</span> department
<span class="token keyword">FROM</span> employees
<span class="token keyword">WHERE</span> department <span class="token operator">=</span> <span class="token string">'Sales'</span><span class="token punctuation">;</span>
</code></pre>
<p>Теперь можно выполнять запросы к представлению <code>sales_employees</code>, как к обычной таблице.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> <span class="token operator">*</span> <span class="token keyword">FROM</span> sales_employees<span class="token punctuation">;</span>
</code></pre>
<h2 id="обновление-представления">Обновление представления</h2>
<p>Для изменения уже существующего представления используется оператор <code>CREATE OR REPLACE VIEW</code>, который позволяет либо создать новое представление, либо обновить существующее, если оно уже есть.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token operator">OR</span> REPLACE <span class="token keyword">VIEW</span> имя_представления <span class="token keyword">AS</span>
<span class="token keyword">SELECT</span> новые_столбцы
<span class="token keyword">FROM</span> таблицы
<span class="token keyword">WHERE</span> условия<span class="token punctuation">;</span>
</code></pre>
<p>Пример :</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token operator">OR</span> REPLACE <span class="token keyword">VIEW</span> sales_employees <span class="token keyword">AS</span>
<span class="token keyword">SELECT</span> employee_id<span class="token punctuation">,</span> first_name<span class="token punctuation">,</span> last_name<span class="token punctuation">,</span> department<span class="token punctuation">,</span> salary
<span class="token keyword">FROM</span> employees
<span class="token keyword">WHERE</span> department <span class="token operator">=</span> <span class="token string">'Sales'</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="удаление-представления">Удаление представления</h2>
<p>Если представление больше не требуется, его можно удалить с помощью оператора <code>DROP VIEW</code>:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">DROP</span> <span class="token keyword">VIEW</span> имя_представления<span class="token punctuation">;</span>
</code></pre>
<p>Пример:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">DROP</span> <span class="token keyword">VIEW</span> sales_employees<span class="token punctuation">;</span>
</code></pre>
<h2 id="обновляемые-и-не-обновляемые-представления">Обновляемые и не обновляемые представления</h2>
<p>MySQL позволяет обновлять данные через представления, если они отвечают определенным условиям. Например, представление должно быть основано на одной таблице и не содержать агрегатных функций (например, <code>SUM</code>, <code>COUNT</code>). Такие представления называются <strong>обновляемыми</strong>.</p>
<p>Пример обновляемого представления:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">VIEW</span> employee_salaries <span class="token keyword">AS</span>
<span class="token keyword">SELECT</span> employee_id<span class="token punctuation">,</span> first_name<span class="token punctuation">,</span> salary
<span class="token keyword">FROM</span> employees<span class="token punctuation">;</span>
</code></pre>
<p>Если выполнить команду <code>UPDATE</code> через это представление, данные изменятся в исходной таблице <code>employees</code>:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">UPDATE</span> employee_salaries
<span class="token keyword">SET</span> salary <span class="token operator">=</span> salary <span class="token operator">+</span> <span class="token number">500</span>
<span class="token keyword">WHERE</span> employee_id <span class="token operator">=</span> <span class="token number">1</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="просмотр-структуры-представления">Просмотр структуры представления</h2>
<p>Для просмотра структуры представления используйте команду <code>SHOW CREATE VIEW</code>:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SHOW</span> <span class="token keyword">CREATE</span> <span class="token keyword">VIEW</span> имя_представления<span class="token punctuation">;</span>
</code></pre>
<p>Пример:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SHOW</span> <span class="token keyword">CREATE</span> <span class="token keyword">VIEW</span> sales_employees<span class="token punctuation">;</span>
</code></pre>
<h1 id="cвязи-и-их-типы">Cвязи и их типы</h1>
<h2 id="определение-2">Определение</h2>
<blockquote>
<p><strong>Реляционная база данных</strong> (РБД) — это система управления данными, где информация хранится в виде связанных таблиц. В таких таблицах<br>
данные организованы в строки (записи) и столбцы (поля), что упрощает<br>
их доступ и управление. Основной принцип РБД — это связь данных через<br>
общие значения (например, идентификаторы(первичные ключи)),<br>
позволяющая эффективно организовывать и искать информацию.</p>
</blockquote>
<p>В реляционных базах данных связи между таблицами являются важным элементом для нормализации и организации данных. Связи описывают, как одна таблица соотносится с другой. В MySQL используются следующие основные типы связей:</p>
<ul>
<li><strong>One-to-One (Один к одному)</strong></li>
<li><strong>One-to-Many (Один ко многим)</strong></li>
<li><strong>Many-to-Many (Многие ко многим)</strong></li>
</ul>
<h2 id="one-to-one-один-к-одному">One-to-One (Один к одному)</h2>
<p>Связь <strong>One-to-One</strong> означает, что каждому записанному элементу в одной таблице соответствует ровно один элемент в другой таблице.</p>
<p>Предположим, у нас есть две таблицы: <code>users</code> и <code>user_profiles</code>. Каждый пользователь может иметь только один профиль.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token comment">-- Таблица пользователей</span>
<span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    user_id <span class="token keyword">INT</span> <span class="token keyword">AUTO_INCREMENT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    username <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">100</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span><span class="token punctuation">,</span>
    email <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">100</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">-- Таблица профилей пользователей</span>
<span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> user_profiles <span class="token punctuation">(</span>
    user_id <span class="token keyword">INT</span> <span class="token keyword">AUTO_INCREMENT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    bio <span class="token keyword">TEXT</span><span class="token punctuation">,</span>
    avatar <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">255</span><span class="token punctuation">)</span><span class="token punctuation">,</span>
    <span class="token keyword">FOREIGN</span> <span class="token keyword">KEY</span> <span class="token punctuation">(</span>user_id<span class="token punctuation">)</span> <span class="token keyword">REFERENCES</span> users<span class="token punctuation">(</span>user_id<span class="token punctuation">)</span> <span class="token keyword">ON</span> <span class="token keyword">DELETE</span> <span class="token keyword">CASCADE</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>В данном примере:</p>
<ul>
<li>Каждый пользователь (<code>users</code>) может иметь только один профиль в таблице <code>user_profiles</code>.</li>
<li>Связь устанавливается через внешний ключ <code>user_id</code>, который в таблице <code>user_profiles</code> ссылается на <code>user_id</code> в таблице <code>users</code>.</li>
<li>Так как и первое и второе является первичным ключом профиль пользователя повторяет уникальны ID самого пользователя.</li>
</ul>
<h2 id="one-to-many-один-ко-многим">One-to-Many (Один ко многим)</h2>
<p>Связь <strong>One-to-Many</strong> означает, что одному элементу в первой таблице могут соответствовать несколько элементов во второй таблице.</p>
<p>Предположим, у нас есть таблицы <code>authors</code> и <code>books</code>. Каждый автор может написать несколько книг, но каждая книга принадлежит только одному автору.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token comment">-- Таблица авторов</span>
<span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> authors <span class="token punctuation">(</span>
    author_id <span class="token keyword">INT</span> <span class="token keyword">AUTO_INCREMENT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    name <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">100</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">-- Таблица книг</span>
<span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> books <span class="token punctuation">(</span>
    book_id <span class="token keyword">INT</span> <span class="token keyword">AUTO_INCREMENT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    title <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">255</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span><span class="token punctuation">,</span>
    author_id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    <span class="token keyword">FOREIGN</span> <span class="token keyword">KEY</span> <span class="token punctuation">(</span>author_id<span class="token punctuation">)</span> <span class="token keyword">REFERENCES</span> authors<span class="token punctuation">(</span>author_id<span class="token punctuation">)</span> <span class="token keyword">ON</span> <span class="token keyword">DELETE</span> <span class="token keyword">CASCADE</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>В данном примере:</p>
<ul>
<li>Один автор может написать несколько книг.</li>
<li>Связь устанавливается через внешний ключ <code>author_id</code>, который в таблице <code>books</code> ссылается на <code>author_id</code> в таблице <code>authors</code>.</li>
</ul>
<h2 id="many-to-many-многие-ко-многим">Many-to-Many (Многие ко многим)</h2>
<p>Связь <strong>Many-to-Many</strong> означает, что одному элементу в первой таблице может соответствовать несколько элементов во второй таблице, и наоборот.</p>
<p>Предположим, у нас есть таблицы <code>students</code> и <code>courses</code>. Студенты могут записываться на несколько курсов, а курсы могут быть посещаемы несколькими студентами.</p>
<p>Для реализации связи “многие ко многим” требуется третья таблица, которая будет содержать внешние ключи от обеих таблиц. Обязательным условием создания связи является создания композитного первичного ключа.</p>
<blockquote>
<p><strong>Композитный первичный ключ</strong> — составной первичный ключ создается, когда вы указываете несколько столбцов для создания одного первичного<br>
ключа. В этом случае каждый отдельный столбец может содержать<br>
повторяющиеся значения, но комбинация этих значений по всем столбцам<br>
должна быть уникальной.</p>
</blockquote>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token comment">-- Таблица студентов</span>
<span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> students <span class="token punctuation">(</span>
    student_id <span class="token keyword">INT</span> <span class="token keyword">AUTO_INCREMENT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    name <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">100</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">-- Таблица курсов</span>
<span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> courses <span class="token punctuation">(</span>
    course_id <span class="token keyword">INT</span> <span class="token keyword">AUTO_INCREMENT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    title <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">100</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>

<span class="token comment">-- Таблица для связи студентов и курсов</span>
<span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> student_courses <span class="token punctuation">(</span>
    student_id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    course_id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span> <span class="token punctuation">(</span>student_id<span class="token punctuation">,</span> course_id<span class="token punctuation">)</span><span class="token punctuation">,</span>
    <span class="token keyword">FOREIGN</span> <span class="token keyword">KEY</span> <span class="token punctuation">(</span>student_id<span class="token punctuation">)</span> <span class="token keyword">REFERENCES</span> students<span class="token punctuation">(</span>student_id<span class="token punctuation">)</span> <span class="token keyword">ON</span> <span class="token keyword">DELETE</span> <span class="token keyword">CASCADE</span><span class="token punctuation">,</span>
    <span class="token keyword">FOREIGN</span> <span class="token keyword">KEY</span> <span class="token punctuation">(</span>course_id<span class="token punctuation">)</span> <span class="token keyword">REFERENCES</span> courses<span class="token punctuation">(</span>course_id<span class="token punctuation">)</span> <span class="token keyword">ON</span> <span class="token keyword">DELETE</span> <span class="token keyword">CASCADE</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>В данном примере:</p>
<ul>
<li>Студенты могут быть записаны на несколько курсов.</li>
<li>Курсы могут включать нескольких студентов.</li>
<li>Связь осуществляется через таблицу <code>student_courses</code>, которая содержит внешние ключи <code>student_id</code> и <code>course_id</code>.</li>
</ul>
<p>Романенко Е.О. // НИТУ МИСИС</p>

