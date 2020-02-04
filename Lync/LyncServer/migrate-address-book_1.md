---
title: Перенос адресной книги
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c904a122f781da08c92c6b1123cfeb1944dd2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Перенос адресной книги

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

**Миграция настроенных правил нормализации в адресной книге**

1.  Найдите в корневом каталоге\_в общей\_папке адресной книги файл rules нормализации для компании\_\_, а затем скопируйте его в корневой каталог в общей папке адресной книги в Lync Server 2013 Pilot pooling.
    
    <div>
    

    > [!NOTE]  
    > Примеры правил нормализации адресных книг установлены в каталог файлов веб-компонентов ABS. Путь <STRONG>$installedDriveLetter: \Program Files\Microsoft Lync Server 2013 \ Web Компонентс\аддресс Book филес\филес\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>. Этот файл можно скопировать и переименовать как &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;в корневой каталог общей папки адресной книги. Например, адресная книга, доступная <STRONG></STRONG>в $serverX&nbsp;, будет выглядеть примерно так: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.

    
    </div>

2.  Используйте текстовый редактор, например Блокнот,\_для открытия файла\_\_\_Rules Normal. txt для компании.

3.  Некоторые типы записей не будут правильно работать в Lync Server 2013. Просмотрите файл на предмет типов записей, описанных в этом шаге, внесите необходимые изменения и сохраните изменения в общей папке адресной книги в вашем пилотном пуле.
    
    Строки, содержащие требуемый пробел или знаки препинания, приводят к сбою правил нормализации, так как эти символы удаляются из строки, вводимой в правила нормализации. Если у вас есть строки, содержащие необходимые пробелы или знаки препинания, необходимо изменить строки. Например, следующая строка может привести к сбою правила нормализации:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    Следующая строка не приводила к сбою правила нормализации:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

