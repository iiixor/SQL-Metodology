---


---

<h1 id="sql.-методологические-указания.">SQL. Методологические указания.</h1>
<h2 id="теория">Теория</h2>
<p>SQL (Structured Query Language // Язык Структурированных Запросов) — это язык программирования, предназначенный для управления и обработки данных в реляционных базах данных.</p>
<h3 id="преимущества">Преимущества</h3>
<p>Преимущества SQL относительно стандартных решений обработки данных заключаются в том, что SQL позволяет обращаться к данным единым запросом, обладает реляционностью и высокой скоростью, благодарю скомпилированным запросам, строгой типизации и продвинутыми алгоритмами поиска и сортировки.</p>
<h2 id="типы-данных-в-mysql">Типы данных в MySQL</h2>
<p>В MySQL типы данных разделены на основные группы:</p>
<ol>
<li><strong>Числовые типы</strong> (<code>Numeric</code>)</li>
<li><strong>Дата и время</strong> (<code>Date and Time</code>)</li>
<li><strong>Строковые типы</strong> (<code>String</code>)</li>
<li><strong>Логические типы</strong> (<code>Boolean</code>)</li>
</ol>
<h3 id="числовые-типы-данных">Числовые типы данных</h3>
<h4 id="целочисленные-типы">Целочисленные типы</h4>

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
</table><p><strong>Примечания:</strong></p>
<ul>
<li><strong>Со знаком</strong>: позволяет использовать отрицательные и положительные числа.</li>
<li><strong>Без знака</strong>: только положительные числа.</li>
</ul>
<h4 id="дробные-типы-числа-с-плавающей-точкой">Дробные типы (Числа с плавающей точкой)</h4>

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
</table><h3 id="дата-и-время">Дата и время</h3>

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
<h3 id="строковые-типы-данных">Строковые типы данных</h3>
<h4 id="символьные-и-текстовые-типы">Символьные и текстовые типы</h4>

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
</table><h4 id="двоичные-типы">Двоичные типы</h4>

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
</table><h3 id="логические-типы-данных">Логические типы данных</h3>

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
<h3 id="прочие-типы-данных">Прочие типы данных</h3>

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
<h2 id="ограничители-в-mysql">Ограничители в MySQL</h2>
<p>Ограничители (constraints) в MySQL помогают обеспечивать целостность данных и устанавливают правила, которым значения в таблице должны соответствовать.</p>
<h3 id="основные-типы-ограничителей">Основные типы ограничителей</h3>
<h4 id="primary-key"><code>PRIMARY KEY</code></h4>
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
<h4 id="not-null"><code>NOT NULL</code></h4>
<p>Ограничитель <code>NOT NULL</code> не позволяет столбцу принимать значение <code>NULL</code>. Это означает, что поле всегда должно содержать данные, и вставка или обновление записи без значения в этом поле вызовет ошибку.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span><span class="token punctuation">,</span>
    username <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">50</span><span class="token punctuation">)</span> <span class="token operator">NOT</span> <span class="token boolean">NULL</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h4 id="unique"><code>UNIQUE</code></h4>
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
<h4 id="композитные-ключи-составные-primary-key-и-unique">Композитные ключи (составные <code>PRIMARY KEY</code> и <code>UNIQUE</code>)</h4>
<p>Композитный (или составной) ключ используется для уникальности комбинации значений двух или более столбцов. Композитный <code>PRIMARY KEY</code> действует как уникальный идентификатор на уровне всей комбинации значений. Является обязательный условием реализации внешней связи Many-to-Many.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> orders <span class="token punctuation">(</span>
    order_id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    product_id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span> <span class="token punctuation">(</span>order_id<span class="token punctuation">,</span> product_id<span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h4 id="foreign-key"><code>FOREIGN KEY</code></h4>
<p>Ограничитель <code>FOREIGN KEY</code> создает связь между таблицами и обеспечивает целостность данных, ограничивая возможные значения ссылками на первичный ключ другой таблицы. Этот тип ограничителя особенно полезен при работе с реляционными данными.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> orders <span class="token punctuation">(</span>
    order_id <span class="token keyword">INT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    user_id <span class="token keyword">INT</span><span class="token punctuation">,</span>
    <span class="token keyword">FOREIGN</span> <span class="token keyword">KEY</span> <span class="token punctuation">(</span>user_id<span class="token punctuation">)</span> <span class="token keyword">REFERENCES</span> users<span class="token punctuation">(</span>id<span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p><code>FOREIGN KEY</code> также поддерживает действия <code>ON DELETE</code> и <code>ON UPDATE</code>, такие как <code>CASCADE</code>, что позволяет автоматически удалять или обновлять связанные записи при изменении данных в таблице-родителе.</p>
<h4 id="check"><code>CHECK</code></h4>
<p>Ограничитель <code>CHECK</code> позволяет задавать условие, которому должны соответствовать значения в столбце. Например, <code>CHECK</code> может ограничить диапазон значений или задать конкретные допустимые значения.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> products <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    price <span class="token keyword">DECIMAL</span><span class="token punctuation">(</span><span class="token number">10</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span> <span class="token keyword">CHECK</span> <span class="token punctuation">(</span>price <span class="token operator">&gt;=</span> <span class="token number">0</span><span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h4 id="default"><code>DEFAULT</code></h4>
<p>Ограничитель <code>DEFAULT</code> определяет значение по умолчанию для столбца, если при вставке записи значение в этом столбце не указано. Это позволяет упростить структуру записей, когда одно и то же значение применяется часто.</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span><span class="token punctuation">,</span>
    is_active <span class="token keyword">TINYINT</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span> <span class="token keyword">DEFAULT</span> <span class="token number">1</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h4 id="auto_increment"><code>AUTO_INCREMENT</code></h4>
<p>Ограничитель <code>AUTO_INCREMENT</code> автоматически увеличивает значение столбца для каждой новой записи. Чаще всего используется для создания уникальных идентификаторов (ID).</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">CREATE</span> <span class="token keyword">TABLE</span> users <span class="token punctuation">(</span>
    id <span class="token keyword">INT</span> <span class="token keyword">PRIMARY</span> <span class="token keyword">KEY</span> <span class="token keyword">AUTO_INCREMENT</span><span class="token punctuation">,</span>
    username <span class="token keyword">VARCHAR</span><span class="token punctuation">(</span><span class="token number">50</span><span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h4 id="unsigned"><code>UNSIGNED</code></h4>
<p>Ограничитель <code>UNSIGNED</code> применяется к числовым столбцам и запрещает использование отрицательных значений или же . <code>UNSIGNED</code> полезен, когда необходимо увеличить максимальный диапазон положительных чисел в столбце.</p>

