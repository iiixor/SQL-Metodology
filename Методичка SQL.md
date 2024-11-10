---


---

<h1 id="mysql.-методологические-указания.">MySQL. Методологические указания.</h1>
<p>Романенко Е.О. // НИТУ МИСИС</p>
<h1 id="теория">Теория</h1>
<h2 id="что-такое-sql">Что такое SQL</h2>
<blockquote>
<p><strong>SQL (Structured Query Language // Язык Структурированных Запросов)</strong> — это язык программирования, предназначенный для управления и обработки данных в реляционных базах данных.</p>
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
<p><strong>Ограничители (constraints) в MySQL</strong> — помогают обеспечивать целостность данных и устанавливают правила, которым значения в таблице должны соответствовать.</p>
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
<p><strong><code>ALTER TABLE</code></strong> — используется для изменения структуры существующей таблицы в MySQL.<br>
С помощью <code>ALTER TABLE</code> можно добавлять, удалять или изменять столбцы, устанавливать или удалять ограничения, а также выполнять другие операции, меняющие структуру таблицы без необходимости её удаления и повторного создания.</p>
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
<p><strong>VIEW</strong> (представление) — это виртуальная таблица в базе данных, которая формируется из результата выполнения SQL-запроса или же заготовленный фильтр уже существующих данных. Представление может включать данные из одной или нескольких таблиц. Оно предоставляет доступ к данным без необходимости их дублирования и облегчает работу с ними, так как вы можете выполнять запросы к представлению как к обычной таблице.</p>
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
<p><strong>Реляционная база данных</strong> (РБД) — это система управления данными, где информация хранится в виде связанных таблиц. В таких таблицах данные организованы в строки (записи) и столбцы (поля), что упрощает<br>
их доступ и управление. Основной принцип РБД — это связь данных через общие значения (например, идентификаторы(первичные ключи)), позволяющая эффективно организовывать и искать информацию.</p>
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
<p><strong>Композитный первичный ключ</strong> — составной первичный ключ создается, когда вы указываете несколько столбцов для создания одного первичного ключа. В этом случае каждый отдельный столбец может содержать повторяющиеся значения, но комбинация этих значений по всем столбцам должна быть уникальной.</p>
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
<h1 id="функции">Функции</h1>
<h2 id="определение-3">Определение</h2>
<blockquote>
<p><strong>Функции в SQL</strong> — это встроенные или пользовательские методы, которые выполняют определенные операции с данными в базе данных. Функции позволяют модифицировать, агрегировать, проверять и преобразовывать данные, делая SQL-запросы более мощными и гибкими. В SQL функции работают с разными типами данных, такими как строки, числа и даты, и помогают выполнять задачи от простых вычислений до сложной обработки данных.</p>
</blockquote>
<h2 id="типы-функций">Типы функций</h2>
<p>SQL функции делят на следующие категории:</p>
<ul>
<li><strong>Агрегатные функции</strong> — обрабатывают несколько строк и возвращают одно значение, например, <code>SUM()</code> для суммирования или <code>AVG()</code> для вычисления среднего.</li>
<li><strong>Строковые функции</strong> — работают с текстом, например, <code>CONCAT()</code> для объединения строк или <code>UPPER()</code> для приведения текста к верхнему регистру.</li>
<li><strong>Числовые функции</strong> — выполняют математические операции, такие как округление или нахождение абсолютного значения.</li>
<li><strong>Функции работы с датами</strong> — позволяют управлять значениями даты и времени, например, <code>NOW()</code> для получения текущего времени.</li>
<li><strong>Логические функции</strong> — помогают проверять условия и обрабатывать логические значения, такие как <code>IF()</code> и <code>CASE</code>.</li>
</ul>
<h2 id="агрегатные-функции">Агрегатные функции</h2>
<p>Агрегатные функции обрабатывают наборы строк и возвращают одно значение для всего набора. Обычно используются с <code>GROUP BY</code>, чтобы сгруппировать данные перед агрегированием.</p>
<ul>
<li><strong><code>COUNT()</code></strong> — подсчитывает количество строк.</li>
<li><strong><code>SUM()</code></strong> — вычисляет сумму значений в группе.</li>
<li><strong><code>AVG()</code></strong> — вычисляет среднее значение.</li>
<li><strong><code>MAX()</code></strong> и <strong><code>MIN()</code></strong> — возвращают максимальное и минимальное значение в группе.</li>
</ul>
<blockquote>
<p>Полная таблица агрегатных функций MySQL представлена в <strong>Приложении</strong></p>
</blockquote>
<p>Пример:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> <span class="token function">AVG</span><span class="token punctuation">(</span>balance<span class="token punctuation">)</span> <span class="token keyword">AS</span> avg_balance <span class="token keyword">FROM</span> users<span class="token punctuation">;</span>
</code></pre>
<p>В данном примере:</p>
<ul>
<li>Найдем средний <code>AVG()</code> баланс пользователя</li>
<li>Назовем колонку с результатом как: <code>avg_balance</code></li>
</ul>
<h2 id="cтроковое-функции">Cтроковое функции</h2>
<p>Строковые функции манипулируют строковыми данными, выполняя такие операции, как конкатенация, изменение регистра и поиск подстрок.</p>
<ul>
<li><strong><code>CONCAT()</code></strong> — объединяет несколько строк в одну.</li>
<li><strong><code>LOWER()</code></strong> и <strong><code>UPPER()</code></strong> — преобразуют строку в нижний или верхний регистр.</li>
<li><strong><code>SUBSTRING()</code></strong> — извлекает подстроку из строки.</li>
<li><strong><code>LENGTH()</code></strong> — возвращает длину строки.</li>
</ul>
<blockquote>
<p>Полная таблица строковых функций MySQL представлена в <strong>Приложении</strong></p>
</blockquote>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">SELECT</span> <span class="token keyword">DISTINCT</span> LOWER<span class="token punctuation">(</span>name<span class="token punctuation">)</span> <span class="token keyword">AS</span> unique_names <span class="token keyword">FROM</span> users<span class="token punctuation">;</span>
</code></pre>
<p>В данном примере:</p>
<ul>
<li><code>LOWER</code> используется для приведения всех выведенных строк к нижнем регистру.</li>
<li>Оператор <code>DISTINCT</code> для получения только уникальных значений.</li>
</ul>
<h1 id="приложение">Приложение</h1>
<p>В данной разделе представлены дополнения к основным материалам методологического указания по MySQL.</p>
<h2 id="таблица-агрегатных-функций-mysql">Таблица агрегатных функций MySQL</h2>

<table>
<thead>
<tr>
<th>Функция</th>
<th>Описание</th>
<th>Пример использования</th>
<th>Результат</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong><code>COUNT()</code></strong></td>
<td>Возвращает количество строк в выборке, которые соответствуют указанным условиям.</td>
<td><code>SELECT COUNT(*) FROM employees;</code></td>
<td>Количество всех строк в таблице</td>
</tr>
<tr>
<td><strong><code>SUM()</code></strong></td>
<td>Возвращает сумму значений указанного столбца (обычно для числовых данных).</td>
<td><code>SELECT SUM(salary) FROM employees;</code></td>
<td>Сумма значений в столбце <code>salary</code></td>
</tr>
<tr>
<td><strong><code>AVG()</code></strong></td>
<td>Возвращает среднее значение указанного столбца.</td>
<td><code>SELECT AVG(salary) FROM employees;</code></td>
<td>Среднее значение <code>salary</code></td>
</tr>
<tr>
<td><strong><code>MIN()</code></strong></td>
<td>Возвращает минимальное значение в столбце.</td>
<td><code>SELECT MIN(salary) FROM employees;</code></td>
<td>Минимальное значение <code>salary</code></td>
</tr>
<tr>
<td><strong><code>MAX()</code></strong></td>
<td>Возвращает максимальное значение в столбце.</td>
<td><code>SELECT MAX(salary) FROM employees;</code></td>
<td>Максимальное значение <code>salary</code></td>
</tr>
<tr>
<td><strong><code>GROUP_CONCAT()</code></strong></td>
<td>Объединяет значения в группе строк в одну строку с указанием разделителя.</td>
<td><code>SELECT GROUP_CONCAT(name) FROM employees;</code></td>
<td>Конкатенация всех имен сотрудников</td>
</tr>
<tr>
<td><strong><code>STDDEV()</code></strong></td>
<td>Возвращает выборочное стандартное отклонение для значений в группе.</td>
<td><code>SELECT STDDEV(salary) FROM employees;</code></td>
<td>Стандартное отклонение <code>salary</code></td>
</tr>
<tr>
<td><strong><code>STDDEV_SAMP()</code></strong></td>
<td>Синоним для <code>STDDEV()</code>, возвращает стандартное отклонение выборки.</td>
<td><code>SELECT STDDEV_SAMP(salary) FROM employees;</code></td>
<td>Стандартное отклонение выборки <code>salary</code></td>
</tr>
<tr>
<td><strong><code>STDDEV_POP()</code></strong></td>
<td>Возвращает стандартное отклонение генеральной совокупности (популяции) для значений в группе.</td>
<td><code>SELECT STDDEV_POP(salary) FROM employees;</code></td>
<td>Стандартное отклонение генеральной совокупности</td>
</tr>
<tr>
<td><strong><code>VARIANCE()</code></strong></td>
<td>Возвращает выборочную дисперсию для значений в группе.</td>
<td><code>SELECT VARIANCE(salary) FROM employees;</code></td>
<td>Выборочная дисперсия <code>salary</code></td>
</tr>
<tr>
<td><strong><code>VAR_SAMP()</code></strong></td>
<td>Синоним для <code>VARIANCE()</code>, возвращает дисперсию выборки.</td>
<td><code>SELECT VAR_SAMP(salary) FROM employees;</code></td>
<td>Дисперсия выборки <code>salary</code></td>
</tr>
<tr>
<td><strong><code>VAR_POP()</code></strong></td>
<td>Возвращает дисперсию совокупности (популяции) для значений в группе.</td>
<td><code>SELECT VAR_POP(salary) FROM employees;</code></td>
<td>Дисперсия совокупности <code>salary</code></td>
</tr>
<tr>
<td><strong><code>BIT_AND()</code></strong></td>
<td>Выполняет побитовую операцию И для всех значений в группе.</td>
<td><code>SELECT BIT_AND(flags) FROM employees;</code></td>
<td>Результат побитового И для <code>flags</code></td>
</tr>
<tr>
<td><strong><code>BIT_OR()</code></strong></td>
<td>Выполняет побитовую операцию ИЛИ для всех значений в группе.</td>
<td><code>SELECT BIT_OR(flags) FROM employees;</code></td>
<td>Результат побитового ИЛИ для <code>flags</code></td>
</tr>
<tr>
<td><strong><code>BIT_XOR()</code></strong></td>
<td>Выполняет побитовую операцию XOR для всех значений в группе.</td>
<td><code>SELECT BIT_XOR(flags) FROM employees;</code></td>
<td>Результат побитового XOR для <code>flags</code></td>
</tr>
<tr>
<td><strong><code>JSON_ARRAYAGG()</code></strong></td>
<td>Возвращает JSON-массив, содержащий значения из группы.</td>
<td><code>SELECT JSON_ARRAYAGG(name) FROM employees;</code></td>
<td>JSON-массив имен сотрудников</td>
</tr>
<tr>
<td><strong><code>JSON_OBJECTAGG()</code></strong></td>
<td>Возвращает JSON-объект, где ключи и значения образуются из значений двух столбцов.</td>
<td><code>SELECT JSON_OBJECTAGG(id, name) FROM employees;</code></td>
<td>JSON-объект с <code>id</code> в качестве ключей и <code>name</code> в качестве значений</td>
</tr>
</tbody>
</table><h2 id="таблица-строковых-функций-mysql">Таблица строковых функций MySQL</h2>

<table>
<thead>
<tr>
<th>Функция</th>
<th>Описание</th>
<th>Пример использования</th>
<th>Результат</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong><code>CONCAT()</code></strong></td>
<td>Объединяет строки.</td>
<td><code>CONCAT('Hello', ' ', 'World')</code></td>
<td><code>'Hello World'</code></td>
</tr>
<tr>
<td><strong><code>CONCAT_WS()</code></strong></td>
<td>Объединяет строки с разделителем между ними.</td>
<td><code>CONCAT_WS(', ', 'apple', 'banana')</code></td>
<td><code>'apple, banana'</code></td>
</tr>
<tr>
<td><strong><code>LOWER()</code></strong></td>
<td>Преобразует строку в нижний регистр.</td>
<td><code>LOWER('HELLO')</code></td>
<td><code>'hello'</code></td>
</tr>
<tr>
<td><strong><code>UPPER()</code></strong></td>
<td>Преобразует строку в верхний регистр.</td>
<td><code>UPPER('hello')</code></td>
<td><code>'HELLO'</code></td>
</tr>
<tr>
<td><strong><code>LENGTH()</code></strong></td>
<td>Возвращает длину строки в байтах.</td>
<td><code>LENGTH('Hello')</code></td>
<td><code>5</code></td>
</tr>
<tr>
<td><strong><code>CHAR_LENGTH()</code></strong></td>
<td>Возвращает количество символов в строке.</td>
<td><code>CHAR_LENGTH('Привет')</code></td>
<td><code>6</code></td>
</tr>
<tr>
<td><strong><code>SUBSTRING()</code></strong></td>
<td>Извлекает подстроку из строки.</td>
<td><code>SUBSTRING('Hello World', 1, 5)</code></td>
<td><code>'Hello'</code></td>
</tr>
<tr>
<td><strong><code>LEFT()</code></strong></td>
<td>Возвращает указанное количество символов с начала строки.</td>
<td><code>LEFT('Hello World', 5)</code></td>
<td><code>'Hello'</code></td>
</tr>
<tr>
<td><strong><code>RIGHT()</code></strong></td>
<td>Возвращает указанное количество символов с конца строки.</td>
<td><code>RIGHT('Hello World', 5)</code></td>
<td><code>'World'</code></td>
</tr>
<tr>
<td><strong><code>REVERSE()</code></strong></td>
<td>Переворачивает строку задом наперед.</td>
<td><code>REVERSE('Hello')</code></td>
<td><code>'olleH'</code></td>
</tr>
<tr>
<td><strong><code>TRIM()</code></strong></td>
<td>Удаляет пробелы или указанные символы с начала и конца строки.</td>
<td><code>TRIM(' Hello ')</code></td>
<td><code>'Hello'</code></td>
</tr>
<tr>
<td><strong><code>LTRIM()</code></strong></td>
<td>Удаляет пробелы только слева от строки.</td>
<td><code>LTRIM(' Hello')</code></td>
<td><code>'Hello'</code></td>
</tr>
<tr>
<td><strong><code>RTRIM()</code></strong></td>
<td>Удаляет пробелы только справа от строки.</td>
<td><code>RTRIM('Hello ')</code></td>
<td><code>'Hello'</code></td>
</tr>
<tr>
<td><strong><code>REPLACE()</code></strong></td>
<td>Заменяет все вхождения подстроки в строке на другую подстроку.</td>
<td><code>REPLACE('Hello World', 'World', 'MySQL')</code></td>
<td><code>'Hello MySQL'</code></td>
</tr>
<tr>
<td><strong><code>INSTR()</code></strong></td>
<td>Возвращает позицию первого вхождения подстроки.</td>
<td><code>INSTR('Hello World', 'World')</code></td>
<td><code>7</code></td>
</tr>
<tr>
<td><strong><code>LOCATE()</code></strong></td>
<td>Похож на <code>INSTR()</code>, но с указанием начальной позиции.</td>
<td><code>LOCATE('o', 'Hello World', 5)</code></td>
<td><code>8</code></td>
</tr>
<tr>
<td><strong><code>POSITION()</code></strong></td>
<td>Возвращает позицию первого вхождения подстроки (синоним для <code>LOCATE()</code>).</td>
<td><code>POSITION('World' IN 'Hello World')</code></td>
<td><code>7</code></td>
</tr>
<tr>
<td><strong><code>ASCII()</code></strong></td>
<td>Возвращает ASCII-код первого символа строки.</td>
<td><code>ASCII('A')</code></td>
<td><code>65</code></td>
</tr>
<tr>
<td><strong><code>CHAR()</code></strong></td>
<td>Возвращает символы по их ASCII-кодам.</td>
<td><code>CHAR(72, 101, 108, 108, 111)</code></td>
<td><code>'Hello'</code></td>
</tr>
<tr>
<td><strong><code>FORMAT()</code></strong></td>
<td>Форматирует число с разделителем для тысяч и заданным количеством десятичных знаков.</td>
<td><code>FORMAT(12345.6789, 2)</code></td>
<td><code>'12,345.68'</code></td>
</tr>
<tr>
<td><strong><code>LPAD()</code></strong></td>
<td>Дополняет строку указанными символами слева до нужной длины.</td>
<td><code>LPAD('123', 5, '0')</code></td>
<td><code>'00123'</code></td>
</tr>
<tr>
<td><strong><code>RPAD()</code></strong></td>
<td>Дополняет строку указанными символами справа до нужной длины.</td>
<td><code>RPAD('123', 5, '0')</code></td>
<td><code>'12300'</code></td>
</tr>
<tr>
<td><strong><code>ELT()</code></strong></td>
<td>Возвращает элемент из списка строк по заданному индексу.</td>
<td><code>ELT(2, 'apple', 'banana', 'cherry')</code></td>
<td><code>'banana'</code></td>
</tr>
<tr>
<td><strong><code>FIELD()</code></strong></td>
<td>Возвращает позицию указанного элемента в списке.</td>
<td><code>FIELD('banana', 'apple', 'banana', 'cherry')</code></td>
<td><code>2</code></td>
</tr>
<tr>
<td><strong><code>FIND_IN_SET()</code></strong></td>
<td>Возвращает позицию строки в списке значений, разделенных запятыми.</td>
<td><code>FIND_IN_SET('b', 'a,b,c')</code></td>
<td><code>2</code></td>
</tr>
<tr>
<td><strong><code>MAKE_SET()</code></strong></td>
<td>Возвращает строку с элементами из списка, соответствующими установленным битам числа.</td>
<td><code>MAKE_SET(5, 'a', 'b', 'c')</code></td>
<td><code>'a,c'</code></td>
</tr>
<tr>
<td><strong><code>SPACE()</code></strong></td>
<td>Возвращает строку, состоящую из заданного количества пробелов.</td>
<td><code>SPACE(5)</code></td>
<td><code>' '</code> (5 пробелов)</td>
</tr>
<tr>
<td><strong><code>QUOTE()</code></strong></td>
<td>Возвращает строку, заключенную в одинарные кавычки и экранирующую специальные символы.</td>
<td><code>QUOTE("Hello 'World'")</code></td>
<td><code>"'Hello \'World\''"</code></td>
</tr>
<tr>
<td><strong><code>SUBSTRING_INDEX()</code></strong></td>
<td>Возвращает часть строки до указанного количества вхождений символа-разделителя.</td>
<td><code>SUBSTRING_INDEX('www.example.com', '.', 2)</code></td>
<td><code>'www.example'</code></td>
</tr>
<tr>
<td><strong><code>INSERT()</code></strong></td>
<td>Вставляет подстроку в указанную позицию в строке, заменяя определенное количество символов.</td>
<td><code>INSERT('Hello World', 7, 5, 'MySQL')</code></td>
<td><code>'Hello MySQL'</code></td>
</tr>
<tr>
<td><strong><code>REPEAT()</code></strong></td>
<td>Повторяет строку указанное количество раз.</td>
<td><code>REPEAT('abc', 3)</code></td>
<td><code>'abcabcabc'</code></td>
</tr>
<tr>
<td><strong><code>HEX()</code></strong></td>
<td>Преобразует строку в шестнадцатеричное значение.</td>
<td><code>HEX('A')</code></td>
<td><code>'41'</code></td>
</tr>
<tr>
<td><strong><code>UNHEX()</code></strong></td>
<td>Преобразует шестнадцатеричное значение обратно в строку.</td>
<td><code>UNHEX('41')</code></td>
<td><code>'A'</code></td>
</tr>
</tbody>
</table>
