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

# <a name="migrate-address-book"></a><span data-ttu-id="bb209-102">Перенос адресной книги</span><span class="sxs-lookup"><span data-stu-id="bb209-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb209-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bb209-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bb209-104">**Миграция настроенных правил нормализации в адресной книге**</span><span class="sxs-lookup"><span data-stu-id="bb209-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="bb209-105">Найдите в корневом каталоге\_в общей\_папке адресной книги файл rules нормализации для компании\_\_, а затем скопируйте его в корневой каталог в общей папке адресной книги в Lync Server 2013 Pilot pooling.</span><span class="sxs-lookup"><span data-stu-id="bb209-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bb209-106">Примеры правил нормализации адресных книг установлены в каталог файлов веб-компонентов ABS.</span><span class="sxs-lookup"><span data-stu-id="bb209-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="bb209-107">Путь <STRONG>$installedDriveLetter: \Program Files\Microsoft Lync Server 2013 \ Web Компонентс\аддресс Book филес\филес\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bb209-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="bb209-108">Этот файл можно скопировать и переименовать как &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;в корневой каталог общей папки адресной книги.</span><span class="sxs-lookup"><span data-stu-id="bb209-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="bb209-109">Например, адресная книга, доступная <STRONG></STRONG>в $serverX&nbsp;, будет выглядеть примерно так: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bb209-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="bb209-110">Используйте текстовый редактор, например Блокнот,\_для открытия файла\_\_\_Rules Normal. txt для компании.</span><span class="sxs-lookup"><span data-stu-id="bb209-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="bb209-111">Некоторые типы записей не будут правильно работать в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb209-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="bb209-112">Просмотрите файл на предмет типов записей, описанных в этом шаге, внесите необходимые изменения и сохраните изменения в общей папке адресной книги в вашем пилотном пуле.</span><span class="sxs-lookup"><span data-stu-id="bb209-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="bb209-113">Строки, содержащие требуемый пробел или знаки препинания, приводят к сбою правил нормализации, так как эти символы удаляются из строки, вводимой в правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="bb209-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="bb209-114">Если у вас есть строки, содержащие необходимые пробелы или знаки препинания, необходимо изменить строки.</span><span class="sxs-lookup"><span data-stu-id="bb209-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="bb209-115">Например, следующая строка может привести к сбою правила нормализации:</span><span class="sxs-lookup"><span data-stu-id="bb209-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="bb209-116">Следующая строка не приводила к сбою правила нормализации:</span><span class="sxs-lookup"><span data-stu-id="bb209-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

