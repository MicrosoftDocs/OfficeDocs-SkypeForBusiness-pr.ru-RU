---
title: Перенос адресной книги
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee0dc4d50fb3b60d4f6a9581d497df11da630122
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Перенос адресной книги

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-09_

Как правило, адресная книга Lync Server 2010 переносится вместе с остальной топологией. Тем не менее, если вы настроили следующие действия в среде Lync Server 2010, вам может потребоваться выполнить некоторые действия, выполняемые после миграции:

  - настроили свойство WMI **PartitionbyOU** для группировки записей адресной книги по подразделениям;

  - настроили правила нормализации адресной книги;

  - изменили значение по умолчанию параметра **UseNormalizationRules** на False.

**Сгруппированные записи адресной книги**

If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.

**Правила нормализации адресной книги**

Если вы настроили правила нормализации адресной книги в среде Lync Server 2010, необходимо перенести эти правила в пилотный пул. Если вы не настраивали правила нормализации адресной книги, то ничего переносить не требуется. По умолчанию для Lync Server 2013 используются те же правила нормализации, что и для Lync Server 2010. Чтобы перенести настроенные правила нормализации, выполните инструкции, приведенные далее в этом разделе.

<div>


> [!NOTE]  
> If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.



</div>

**Параметр UseNormalizationRules со значением False**

Если задать для параметра **UseNormalizationRules** значение false, чтобы пользователи могли использовать номера телефонов, как они определены в доменных службах Active Directory без применения правил нормализации Lync Server 2013, необходимо задать для параметров **UseNormalizationRules** и **IgnoreGenericRules** значение true. Для этого выполните инструкции, приведенные далее в этом разделе.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Перенос настроенных правил нормализации адресной книги

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

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Задание значения True для параметров UseNormalizationRules и IgnoreGenericRules

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните одно из указанных ниже действий.
    
      - Если развертывание включает только Lync Server 2013, выполните следующий командлет на глобальном уровне, чтобы изменить значения для **UseNormalizationRules** и **IgnoreGenericRules** на true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Если в развертывании имеется сочетание Lync Server 2013 и Lync Server 2010 или Office Communications Server 2007 R2, выполните следующий командлет и назначьте его каждому пулу Lync Server 2013 в топологии:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Дождитесь, пока репликация центрального хранилища управления не будет выполняться во всех пулах.

4.  Измените файл правил нормализации телефона в разделе " \_ \_ нормализация номера телефона компании \_ \_Rules.txt", чтобы развертывание было ясно на содержимое. Файл находится на общем файловом ресурсе каждого пула Lync Server 2013. Если файл отсутствует, создайте пустой файл с именем " \_ \_ нормализация номера телефона компании \_ \_Rules.txt".

5.  Подождите несколько минут, пока для всех интерфейсных пулов не будут прочитаны новые файлы.

6.  Выполните следующий командлет на каждом пуле Lync Server 2013 в развертывании:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

