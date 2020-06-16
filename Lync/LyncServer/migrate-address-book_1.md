---
title: Перенос адресной книги
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937bf9dfff07591ea12a2c78604ab82fa34e97f6
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Перенос адресной книги

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

**Перенос настроенных правил нормализации адресной книги**

1.  Найдите \_ \_ \_Rules.txt файл нормализации номера телефона компании \_ в корне общей папки адресной книги и скопируйте его в корневую папку адресной книги в пилотном пуле Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Образцы правил нормализации адресной книги установлены в каталоге, содержащем файлы веб-компонента службы адресной книги. Путь — <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>. Этот файл можно скопировать и переименовать как &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; в корневой каталог общей папки адресной книги. Например, адресная книга предоставляется в <STRONG>$serverX</STRONG>, &nbsp; путь будет выглядеть следующим образом: <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.

    
    </div>

2.  Используйте текстовый редактор, например "Блокнот", чтобы открыть \_ \_ \_Rules.txt файл нормализации номера телефона компании \_ .

3.  Некоторые типы записей не будут правильно работать в Lync Server 2013. Просмотрите файл, чтобы найти записи такого типа, измените их требуемым образом и сохраните изменения в общей папке адресной книги в пилотном пуле.
    
    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    Следующая строка не приведет к сбою правила нормализации.
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

