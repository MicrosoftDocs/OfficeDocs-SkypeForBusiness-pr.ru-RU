---
title: Перенос адресной книги
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'В целом наряду с топологией переносится в адресной книге. Тем не менее необходимо выполнить некоторые действия после переноса, если настроены следующие в старой среды:'
ms.openlocfilehash: 14c9194b8c32ab5db64096c2aa3308a31812c6f8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030471"
---
# <a name="migrate-address-book"></a><span data-ttu-id="394ed-104">Перенос адресной книги</span><span class="sxs-lookup"><span data-stu-id="394ed-104">Migrate Address Book</span></span>

<span data-ttu-id="394ed-105">В целом наряду с топологией переносится в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="394ed-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="394ed-106">Тем не менее необходимо выполнить некоторые действия после переноса, если настроены следующие в старой среды:</span><span class="sxs-lookup"><span data-stu-id="394ed-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 
  
- <span data-ttu-id="394ed-107">Задайте свойство WMI **PartitionbyOU** для группировки записей адресной книги с подразделение (OU).</span><span class="sxs-lookup"><span data-stu-id="394ed-107">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span> 
    
- <span data-ttu-id="394ed-108">Настроить правила нормализации адресной книги.</span><span class="sxs-lookup"><span data-stu-id="394ed-108">Customized the Address Book normalization rules.</span></span>
    
- <span data-ttu-id="394ed-109">Изменено значение по умолчанию параметра **UseNormalizationRules** на False.</span><span class="sxs-lookup"><span data-stu-id="394ed-109">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 
    
 <span data-ttu-id="394ed-110">**Сгруппированные записи адресной книги**</span><span class="sxs-lookup"><span data-stu-id="394ed-110">**Grouped Address Book Entries**</span></span>
  
<span data-ttu-id="394ed-111">Если свойство **PartitionbyOU** WMI задано значение True, чтобы создать адресные книги для каждого Подразделения, необходимо задать атрибут Active Directory **msRTCSIP-GroupingId** пользователей и контактов, чтобы продолжить группировки записей адресной книги.</span><span class="sxs-lookup"><span data-stu-id="394ed-111">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="394ed-112">Чтобы ограничить область поиска адресной книги может потребоваться группировки записей адресной книги.</span><span class="sxs-lookup"><span data-stu-id="394ed-112">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="394ed-113">Чтобы использовать атрибут **msRTCSIP-GroupingId** , написать сценарий для заполнения атрибута, назначение такое же значение для всех пользователей, которые нужно сгруппировать.</span><span class="sxs-lookup"><span data-stu-id="394ed-113">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="394ed-114">Например назначьте одно значение для всех пользователей в Подразделении.</span><span class="sxs-lookup"><span data-stu-id="394ed-114">For example, assign a single value for all the users in an OU.</span></span> 
  
 <span data-ttu-id="394ed-115">**Правила нормализации адресной книги**</span><span class="sxs-lookup"><span data-stu-id="394ed-115">**Address Book Normalization Rules**</span></span>
  
<span data-ttu-id="394ed-116">Если настраиваемые правила нормализации адресной книги в старой среды необходимо перенести настраиваемых правил пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="394ed-116">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="394ed-117">Если не были указаны пользователем правила нормализации адресной книги, вы не для переноса для службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="394ed-117">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="394ed-118">Правила нормализации по умолчанию для Скайп для Business Server 2019 такие же, как правила по умолчанию при установке прежних версий.</span><span class="sxs-lookup"><span data-stu-id="394ed-118">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="394ed-119">Выполните процедуру, описанную далее в этом разделе перенос правил нормализации настраиваемая.</span><span class="sxs-lookup"><span data-stu-id="394ed-119">Follow the procedure later in this section to migrate customized normalization rules.</span></span>
  
> [!NOTE]
> <span data-ttu-id="394ed-120">Если организация использует удаленного управления звонками и настроенных правил нормализации адресной книги, необходимо выполнить процедуры в этом разделе прежде чем можно будет использовать удаленное управление звонками.</span><span class="sxs-lookup"><span data-stu-id="394ed-120">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="394ed-121">Процедуры необходимо быть членом группы RTCUniversalServerAdmins или эквивалентные права.</span><span class="sxs-lookup"><span data-stu-id="394ed-121">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 
  
 <span data-ttu-id="394ed-122">**Параметр UseNormalizationRules имеет значение False**</span><span class="sxs-lookup"><span data-stu-id="394ed-122">**UseNormalizationRules Set to False**</span></span>
  
<span data-ttu-id="394ed-123">При установке значения для **UseNormalizationRules** значение False, чтобы пользователи могли использовать номера телефонов, как они определены в доменных службах Active Directory без необходимости Скайп для Business Server 2019 применения правил нормализации, необходимо задать \*\* UseNormalizationRules\*\* и параметры **IgnoreGenericRules** на True.</span><span class="sxs-lookup"><span data-stu-id="394ed-123">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="394ed-124">Выполните процедуру, описанную далее в этом разделе для этих параметров на значение True.</span><span class="sxs-lookup"><span data-stu-id="394ed-124">Follow the procedure later in this section to set these parameters to True.</span></span> 
  
## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="394ed-125">Перенос адресной книги настроенных правил нормализации</span><span class="sxs-lookup"><span data-stu-id="394ed-125">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="394ed-126">Найдите файл Company_Phone_Number_Normalization_Rules.txt в корне общей папки адресной книги и скопируйте его в корень общей папки адресной книги в вашей Скайп для пилотного пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="394ed-126">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="394ed-127">Примеры правил нормализации адресной книги установленные ABS каталога используемого веб-компонент файла.</span><span class="sxs-lookup"><span data-stu-id="394ed-127">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="394ed-128">— Это путь **$installedDriveLetter: \Program Files\Microsoft Скайп для Business Server 2019\Web Components\Address книги Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="394ed-128">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="394ed-129">Этот файл можно скопировать и переименован как **Company_Phone_Number_Normalization_Rules.txt** в корневой каталог адресной книги общей папки.</span><span class="sxs-lookup"><span data-stu-id="394ed-129">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="394ed-130">Например, в адресной книге, совместно в **$serverX**путь будет аналогичен: \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="394ed-130">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 
  
2. <span data-ttu-id="394ed-131">Используйте текстовый редактор, например "Блокнот", чтобы открыть файл Company_Phone_Number_Normalization_Rules.txt.</span><span class="sxs-lookup"><span data-stu-id="394ed-131">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>
    
3. <span data-ttu-id="394ed-132">Определенные типы записей не будет работать в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="394ed-132">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="394ed-133">Просмотрите файл для типов записей, описанного на этом шаге, при необходимости изменить и сохранить изменения в общую папку адресной книги в пилотном пуле.</span><span class="sxs-lookup"><span data-stu-id="394ed-133">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="394ed-134">Строки, содержащие требуемые пробелов и знаков препинания причина правил нормализации к сбою, так как эти символы удаляются из строки, полученный правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="394ed-134">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="394ed-135">Если у вас есть строк, содержащих необходимые пробелов и знаков препинания, необходимо изменить строк.</span><span class="sxs-lookup"><span data-stu-id="394ed-135">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="394ed-136">Например следующая строка приведет к сбою правила нормализации:</span><span class="sxs-lookup"><span data-stu-id="394ed-136">For example, the following string would cause the normalization rule to fail:</span></span>
    
  ```
  \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
  ```

    <span data-ttu-id="394ed-137">Следующая строка не приведет к сбою правила нормализации:</span><span class="sxs-lookup"><span data-stu-id="394ed-137">The following string would not cause the normalization rule to fail:</span></span>
    
  ```
  \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
  ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="394ed-138">Чтобы задать UseNormalizationRules и IgnoreGenericRules на true</span><span class="sxs-lookup"><span data-stu-id="394ed-138">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="394ed-139">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп Microsoft для Business Server 2019**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="394ed-139">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="394ed-140">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="394ed-140">Do one of the following:</span></span>
    
  - <span data-ttu-id="394ed-141">Если в развертывании имеется только Скайп для 2019 Business Server, выполните следующий командлет на глобальном уровне, чтобы изменить значения для **UseNormalizationRules** и **IgnoreGenericRules** на True:</span><span class="sxs-lookup"><span data-stu-id="394ed-141">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 
    
  ```
  Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
  
  ```

  - <span data-ttu-id="394ed-142">Если развертывание включает сочетание Скайп Business Server 2019 и устаревшие установки, выполните следующий командлет и назначьте его для каждого Скайп для пула Business Server 2019 в топологии:</span><span class="sxs-lookup"><span data-stu-id="394ed-142">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>
    
  ```
  New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
  
  ```

3. <span data-ttu-id="394ed-143">Дождитесь репликации хранилища централизованного управления будет выполнена для всех пулов.</span><span class="sxs-lookup"><span data-stu-id="394ed-143">Wait for Central Management store replication to occur on all pools.</span></span>
    
4. <span data-ttu-id="394ed-144">Измените файл правил нормализации телефонных, «Company_Phone_Number_Normalization_Rules.txt», для развертывания для очистки содержимого.</span><span class="sxs-lookup"><span data-stu-id="394ed-144">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="394ed-145">Файл находится в файловом ресурсе каждого Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="394ed-145">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="394ed-146">Если файл не существует, создайте пустой файл с именем «Company_Phone_Number_Normalization_Rules.txt».</span><span class="sxs-lookup"><span data-stu-id="394ed-146">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>
    
5. <span data-ttu-id="394ed-147">Подождите несколько минут для всех пулов переднего плана не будут прочитаны новые файлы.</span><span class="sxs-lookup"><span data-stu-id="394ed-147">Wait several minutes for all Front End pools to read the new files.</span></span>
    
6. <span data-ttu-id="394ed-148">Выполните следующий командлет на каждом Скайп для Business Server 2019 пула в развертывании:</span><span class="sxs-lookup"><span data-stu-id="394ed-148">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>
    
  ```
  Update-CsAddressBook
  
  ```


