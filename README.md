# uXmlExport

Шаблонная выгрузка из БД Firebird в Xml. В исходный xml-шаблон проставляются переменные, которые равны именам полей из запроса. В процессе парсинга, переменные подменяются значениями полей запроса. На каждую строку запроса создается отдельный xml-файл.

#### Создание объекта класса.

    XmlExport = TXmlExport.Create(Database); // где Database объект TFDConnection
    XmlExport.Xml = Xml; // Xml-шаблон выгрузки, принимает String;
    XmlExport.Sql = Sql; // Sql-запрос, по которому будет формироваться набор данных для выгрузки

Класс унаследован от TThread и является Suspend, поэтому, после создания экземпляра класса, нужно вызвать метод Run для запуска потока.

#### Запуск выгрузки

    XmlExport.Run;



