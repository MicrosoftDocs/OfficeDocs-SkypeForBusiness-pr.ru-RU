---
title: Миграция адресной книги
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
ms.openlocfilehash: e68dbe4db6ee9ac6b9bd758b23a575089019f6c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="43d2d-102">Миграция адресной книги</span><span class="sxs-lookup"><span data-stu-id="43d2d-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43d2d-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="43d2d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="43d2d-104">**Перенос настроенных правил нормализации адресной книги**</span><span class="sxs-lookup"><span data-stu-id="43d2d-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="43d2d-105">Найдите файл\_\_Rules\_(\_правила нормализации) телефонных номеров компаний в корне общей папки адресной книги и скопируйте его в корневую папку адресной книги в пилотном пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43d2d-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43d2d-106">Образцы правил нормализации адресной книги установлены в каталоге, содержащем файлы веб-компонента службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="43d2d-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="43d2d-107">Путь — <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="43d2d-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="43d2d-108">Этот файл можно скопировать и переименовать как &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;в корневой каталог общей папки адресной книги.</span><span class="sxs-lookup"><span data-stu-id="43d2d-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="43d2d-109">Например, адресная книга предоставляется в <STRONG>$serverX</STRONG>,&nbsp;путь будет выглядеть следующим образом: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="43d2d-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="43d2d-110">Используйте текстовый редактор, например "Блокнот",\_для открытия файла\_\_\_правил нормализации номера телефона компании. txt.</span><span class="sxs-lookup"><span data-stu-id="43d2d-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="43d2d-111">Некоторые типы записей не будут правильно работать в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43d2d-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="43d2d-112">Просмотрите файл, чтобы найти записи такого типа, измените их требуемым образом и сохраните изменения в общей папке адресной книги в пилотном пуле.</span><span class="sxs-lookup"><span data-stu-id="43d2d-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="43d2d-p103">Строки, содержащие обязательный пробел или знак пунктуации, приведут к сбою правила нормализации, поскольку эти символы удаляются из строки при ее вводе в правило. Если у вас есть строки с обязательным пробелом или знаком пунктуации, их нужно изменить. Например, следующая строка приведет к сбою правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="43d2d-p103">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="43d2d-116">Следующая строка не приведет к сбою правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="43d2d-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

