---
title: Перенос адресной книги
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2293b7ad3e5ac14071bae4d5ecb935c24cfbb335
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="1996e-102">Перенос адресной книги</span><span class="sxs-lookup"><span data-stu-id="1996e-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1996e-103">_**Тема последнего изменения:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="1996e-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="1996e-104">Как правило, адресная книга Lync Server 2010 переносится вместе с оставшейся частью вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="1996e-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="1996e-105">Тем не менее, если вы настроили указанные ниже действия в среде Lync Server 2010, вам может потребоваться выполнить некоторые шаги после миграции.</span><span class="sxs-lookup"><span data-stu-id="1996e-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="1996e-106">Установите свойство WMI **партитионбйоу** для группировки записей в адресную книгу по организационному подразделению (OU).</span><span class="sxs-lookup"><span data-stu-id="1996e-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="1996e-107">Настроены правила нормализации адресных книг.</span><span class="sxs-lookup"><span data-stu-id="1996e-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="1996e-108">Изменение значения по умолчанию для параметра **усенормализатионрулес** на false.</span><span class="sxs-lookup"><span data-stu-id="1996e-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="1996e-109">**Группировка записей в адресную книгу**</span><span class="sxs-lookup"><span data-stu-id="1996e-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="1996e-110">Если для свойства **партитионбйоу** WMI установлено значение true, чтобы создать адресные книги для каждого подразделения, необходимо задать атрибут **msRTCSIP-граупингид** Active Directory для пользователей и контактов, если вы хотите продолжить группировку записей в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="1996e-110">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="1996e-111">Возможно, вам потребуется сгруппировать записи в адресную книгу, чтобы ограничить область поиска в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="1996e-111">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="1996e-112">Чтобы использовать атрибут **msRTCSIP-граупингид** , напишите сценарий для заполнения атрибута и назначайте одинаковые значения для всех пользователей, которые нужно сгруппировать.</span><span class="sxs-lookup"><span data-stu-id="1996e-112">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="1996e-113">Например, вы назначаете одно значение для всех пользователей в подразделении.</span><span class="sxs-lookup"><span data-stu-id="1996e-113">For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="1996e-114">**Правила нормализации адресных книг**</span><span class="sxs-lookup"><span data-stu-id="1996e-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="1996e-115">Если вы настроили правила нормализации адресных книг в среде Lync Server 2010, вы должны перенести настроенные правила в ваш пилотный пул.</span><span class="sxs-lookup"><span data-stu-id="1996e-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="1996e-116">Если вы не настраиваете правила нормализации адресных книг, вы не можете выполнить миграцию для службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="1996e-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="1996e-117">Правила нормализации по умолчанию для Lync Server 2013 совпадают с правилами по умолчанию для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1996e-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="1996e-118">Выполните действия, описанные ниже в этом разделе, чтобы перенести настраиваемые правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="1996e-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1996e-119">Если в вашей организации используется удаленное управление звонками и настроены правила нормализации адресных книг, необходимо выполнить описанные ниже действия, прежде чем можно будет использовать удаленное управление звонками.</span><span class="sxs-lookup"><span data-stu-id="1996e-119">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="1996e-120">Процедура требует членства в группе Рткуниверсалсерверадминс или эквивалентных прав.</span><span class="sxs-lookup"><span data-stu-id="1996e-120">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="1996e-121">**Для Усенормализатионрулес задано значение false**</span><span class="sxs-lookup"><span data-stu-id="1996e-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="1996e-122">Если для **усенормализатионрулес** задано значение false, чтобы пользователи могли использовать номера телефонов, определенные в доменных службах Active Directory без применения правил нормализации для Lync Server 2013, необходимо установить параметр \*\*усенормализатионрулес. \*\*и **игнореженерикрулес** для параметров значения истина.</span><span class="sxs-lookup"><span data-stu-id="1996e-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="1996e-123">Выполните действия, описанные ниже в этом разделе, чтобы установить для этих параметров значение true.</span><span class="sxs-lookup"><span data-stu-id="1996e-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="1996e-124">Миграция настроенных правил нормализации в адресной книге</span><span class="sxs-lookup"><span data-stu-id="1996e-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="1996e-125">Найдите в корневом каталоге\_в общей\_папке адресной книги файл rules нормализации для компании\_\_, а затем скопируйте его в корневой каталог в общей папке адресной книги в Lync Server 2013 Pilot pooling.</span><span class="sxs-lookup"><span data-stu-id="1996e-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1996e-126">Примеры правил нормализации адресных книг установлены в каталог файлов веб-компонентов ABS.</span><span class="sxs-lookup"><span data-stu-id="1996e-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="1996e-127">Путь <STRONG>$installedDriveLetter: \Program Files\Microsoft Lync Server 2013 \ Web Компонентс\аддресс Book Филес\филес\ сампле_компани_фоне_нумбер_нормализатион_рулес. txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1996e-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="1996e-128">Этот файл можно скопировать и переименовать как &nbsp; <STRONG>компани_фоне_нумбер_нормализатион_рулес. txt</STRONG> &nbsp;в корневой каталог общей папки адресной книги.</span><span class="sxs-lookup"><span data-stu-id="1996e-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="1996e-129">Например, адресная книга, доступная <STRONG></STRONG>в $serverX&nbsp;, будет выглядеть примерно так: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1996e-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="1996e-130">Используйте текстовый редактор, например Блокнот,\_для открытия файла\_\_\_Rules Normal. txt для компании.</span><span class="sxs-lookup"><span data-stu-id="1996e-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="1996e-131">Некоторые типы записей не будут правильно работать в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1996e-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="1996e-132">Просмотрите файл на предмет типов записей, описанных в этом шаге, внесите необходимые изменения и сохраните изменения в общей папке адресной книги в вашем пилотном пуле.</span><span class="sxs-lookup"><span data-stu-id="1996e-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="1996e-133">Строки, содержащие требуемый пробел или знаки препинания, приводят к сбою правил нормализации, так как эти символы удаляются из строки, вводимой в правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="1996e-133">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="1996e-134">Если у вас есть строки, содержащие необходимые пробелы или знаки препинания, необходимо изменить строки.</span><span class="sxs-lookup"><span data-stu-id="1996e-134">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="1996e-135">Например, следующая строка может привести к сбою правила нормализации:</span><span class="sxs-lookup"><span data-stu-id="1996e-135">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="1996e-136">Следующая строка не приводила к сбою правила нормализации:</span><span class="sxs-lookup"><span data-stu-id="1996e-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="1996e-137">Чтобы установить для Усенормализатионрулес и Игнореженерикрулес значение true,</span><span class="sxs-lookup"><span data-stu-id="1996e-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="1996e-138">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1996e-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1996e-139">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1996e-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="1996e-140">Если развертывание включает только сервер Lync Server 2013, выполните следующий командлет на глобальном уровне, чтобы изменить значения для **усенормализатионрулес** и **игнореженерикрулес** на true:</span><span class="sxs-lookup"><span data-stu-id="1996e-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="1996e-141">Если в развертывании есть сочетание Lync Server 2013 и Lync Server 2010 или Office Communications Server 2007 R2, запустите следующий командлет и назначьте его каждому пулу Lync Server 2013 в топологии.</span><span class="sxs-lookup"><span data-stu-id="1996e-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="1996e-142">Дождитесь, когда репликация хранилища центрального управления будет выполняться на всех пулах.</span><span class="sxs-lookup"><span data-stu-id="1996e-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="1996e-143">Измените файл правил нормализации\_телефонной линии "\_\_\_правила нормализации для телефонной номера компании. txt" для развертывания, чтобы очистить содержимое.</span><span class="sxs-lookup"><span data-stu-id="1996e-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="1996e-144">Файл находится в общей папке каждого пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1996e-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="1996e-145">Если файл отсутствует, создайте пустой файл\_с именем "\_\_\_Rules Normal. txt" для номера компании.</span><span class="sxs-lookup"><span data-stu-id="1996e-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="1996e-146">Подождите несколько минут, пока все клиентские пулы смогут прочитать новые файлы.</span><span class="sxs-lookup"><span data-stu-id="1996e-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="1996e-147">Выполните следующий командлет на каждом пуле Lync Server 2013 в развертывании:</span><span class="sxs-lookup"><span data-stu-id="1996e-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

