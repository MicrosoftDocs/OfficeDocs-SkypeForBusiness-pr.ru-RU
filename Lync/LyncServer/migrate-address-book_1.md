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
ms.openlocfilehash: 5f0e67dfb8e7902b2d6a0c89c327b13fb00736ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503666"
---
# <a name="migrate-address-book"></a>Перенос адресной книги

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
    
    Строки, содержащие обязательный пробел или знак пунктуации, приведут к сбою правила нормализации, поскольку эти символы удаляются из строки при ее вводе в правило. Если у вас есть строки с обязательным пробелом или знаком пунктуации, их нужно изменить. Например, следующая строка приведет к сбою правила нормализации.
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    Следующая строка не приведет к сбою правила нормализации.
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

