---
title: Перенос адресной книги
description: Перенос адресной книги.
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
ms.openlocfilehash: ad6acd8cca58aa4e09e21b9b45cbdddec527b5f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579395"
---
# <a name="migrate-address-book"></a><span data-ttu-id="42818-103">Перенос адресной книги</span><span class="sxs-lookup"><span data-stu-id="42818-103">Migrate Address Book</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42818-104">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="42818-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="42818-105">Как правило, адресная книга Lync Server 2010 переносится вместе с остальной топологией.</span><span class="sxs-lookup"><span data-stu-id="42818-105">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="42818-106">Тем не менее, если вы настроили следующие действия в среде Lync Server 2010, вам может потребоваться выполнить некоторые действия, выполняемые после миграции:</span><span class="sxs-lookup"><span data-stu-id="42818-106">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="42818-107">настроили свойство WMI **PartitionbyOU** для группировки записей адресной книги по подразделениям;</span><span class="sxs-lookup"><span data-stu-id="42818-107">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="42818-108">настроили правила нормализации адресной книги;</span><span class="sxs-lookup"><span data-stu-id="42818-108">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="42818-109">изменили значение по умолчанию параметра **UseNormalizationRules** на False.</span><span class="sxs-lookup"><span data-stu-id="42818-109">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="42818-110">**Сгруппированные записи адресной книги**</span><span class="sxs-lookup"><span data-stu-id="42818-110">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="42818-p102">Если вы задали для свойства WMI **PartitionbyOU** значение True, чтобы создать адресные книги для каждого подразделения, вам нужно задать атрибут Active Directory **msRTCSIP-GroupingId** для пользователей и контактов, если вы хотите, чтобы записи адресной книги были по-прежнему сгруппированы. Группировка записей адресной книги может потребоваться для ограничения области поиска в адресной книге. Чтобы использовать атрибут **msRTCSIP-GroupingId**, создайте сценарий для его заполнения и присвойте одинаковое значение всем пользователям, которых необходимо объединить в одну группу. Например, присвойте одинаковое значение всем пользователям определенного подразделения.</span><span class="sxs-lookup"><span data-stu-id="42818-p102">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="42818-115">**Правила нормализации адресной книги**</span><span class="sxs-lookup"><span data-stu-id="42818-115">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="42818-116">Если вы настроили правила нормализации адресной книги в среде Lync Server 2010, необходимо перенести эти правила в пилотный пул.</span><span class="sxs-lookup"><span data-stu-id="42818-116">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="42818-117">Если вы не настраивали правила нормализации адресной книги, то ничего переносить не требуется.</span><span class="sxs-lookup"><span data-stu-id="42818-117">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="42818-118">По умолчанию для Lync Server 2013 используются те же правила нормализации, что и для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="42818-118">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="42818-119">Чтобы перенести настроенные правила нормализации, выполните инструкции, приведенные далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="42818-119">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42818-p104">Если в вашей организации используется удаленное управление звонками и вы настроили правила нормализации адресной книги, то прежде чем использовать удаленное управление звонками, вам нужно выполнить инструкции, приведенные в этом разделе. Для их выполнения необходимо быть членом группы RTCUniversalServerAdmins или иметь аналогичные права.</span><span class="sxs-lookup"><span data-stu-id="42818-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="42818-122">**Параметр UseNormalizationRules со значением False**</span><span class="sxs-lookup"><span data-stu-id="42818-122">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="42818-123">Если задать для параметра **UseNormalizationRules** значение false, чтобы пользователи могли использовать номера телефонов, как они определены в доменных службах Active Directory без применения правил нормализации Lync Server 2013, необходимо задать для параметров **UseNormalizationRules** и **IgnoreGenericRules** значение true.</span><span class="sxs-lookup"><span data-stu-id="42818-123">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="42818-124">Для этого выполните инструкции, приведенные далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="42818-124">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="42818-125">Перенос настроенных правил нормализации адресной книги</span><span class="sxs-lookup"><span data-stu-id="42818-125">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="42818-126">Найдите \_ \_ \_Rules.txt файл нормализации номера телефона компании \_ в корне общей папки адресной книги и скопируйте его в корневую папку адресной книги в пилотном пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42818-126">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42818-127">Образцы правил нормализации адресной книги установлены в каталоге, содержащем файлы веб-компонента службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="42818-127">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="42818-128">Путь — <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="42818-128">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="42818-129">Этот файл можно скопировать и переименовать как &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; в корневой каталог общей папки адресной книги.</span><span class="sxs-lookup"><span data-stu-id="42818-129">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="42818-130">Например, адресная книга предоставляется в <STRONG>$serverX</STRONG>, &nbsp; путь будет выглядеть следующим образом: <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="42818-130">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="42818-131">Используйте текстовый редактор, например "Блокнот", чтобы открыть \_ \_ \_Rules.txt файл нормализации номера телефона компании \_ .</span><span class="sxs-lookup"><span data-stu-id="42818-131">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="42818-132">Некоторые типы записей не будут правильно работать в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42818-132">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="42818-133">Просмотрите файл, чтобы найти записи такого типа, измените их требуемым образом и сохраните изменения в общей папке адресной книги в пилотном пуле.</span><span class="sxs-lookup"><span data-stu-id="42818-133">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="42818-p108">Строки, содержащие обязательный пробел или знак пунктуации, приведут к сбою правила нормализации, поскольку эти символы удаляются из строки при ее вводе в правило. Если у вас есть строки с обязательным пробелом или знаком пунктуации, их нужно изменить. Например, следующая строка приведет к сбою правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="42818-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="42818-137">Следующая строка не приведет к сбою правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="42818-137">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="42818-138">Задание значения True для параметров UseNormalizationRules и IgnoreGenericRules</span><span class="sxs-lookup"><span data-stu-id="42818-138">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="42818-139">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="42818-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="42818-140">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="42818-140">Do one of the following:</span></span>
    
      - <span data-ttu-id="42818-141">Если развертывание включает только Lync Server 2013, выполните следующий командлет на глобальном уровне, чтобы изменить значения для **UseNormalizationRules** и **IgnoreGenericRules** на true:</span><span class="sxs-lookup"><span data-stu-id="42818-141">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="42818-142">Если в развертывании имеется сочетание Lync Server 2013 и Lync Server 2010 или Office Communications Server 2007 R2, выполните следующий командлет и назначьте его каждому пулу Lync Server 2013 в топологии:</span><span class="sxs-lookup"><span data-stu-id="42818-142">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="42818-143">Дождитесь, пока репликация центрального хранилища управления не будет выполняться во всех пулах.</span><span class="sxs-lookup"><span data-stu-id="42818-143">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="42818-144">Измените файл правил нормализации телефона в разделе " \_ \_ нормализация номера телефона компании \_ \_Rules.txt", чтобы развертывание было ясно на содержимое.</span><span class="sxs-lookup"><span data-stu-id="42818-144">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="42818-145">Файл находится на общем файловом ресурсе каждого пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42818-145">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="42818-146">Если файл отсутствует, создайте пустой файл с именем " \_ \_ нормализация номера телефона компании \_ \_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="42818-146">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="42818-147">Подождите несколько минут, пока для всех интерфейсных пулов не будут прочитаны новые файлы.</span><span class="sxs-lookup"><span data-stu-id="42818-147">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="42818-148">Выполните следующий командлет на каждом пуле Lync Server 2013 в развертывании:</span><span class="sxs-lookup"><span data-stu-id="42818-148">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

