---
title: Перенос адресной книги
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'В целом наряду с топологией переносится в адресной книге. Тем не менее необходимо выполнить некоторые действия после переноса, если настроены следующие в старой среды:'
ms.openlocfilehash: 728ae97270cd8451178c6ef962f05e0351118119
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238426"
---
# <a name="migrate-address-book"></a><span data-ttu-id="a8f7c-104">Перенос адресной книги</span><span class="sxs-lookup"><span data-stu-id="a8f7c-104">Migrate Address Book</span></span>

<span data-ttu-id="a8f7c-105">В целом наряду с топологией переносится в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="a8f7c-106">Тем не менее необходимо выполнить некоторые действия после переноса, если настроены следующие в старой среды:</span><span class="sxs-lookup"><span data-stu-id="a8f7c-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="a8f7c-107">Настроить правила нормализации адресной книги.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="a8f7c-108">Изменено значение по умолчанию параметра **UseNormalizationRules** на False.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="a8f7c-109">**Правила нормализации адресной книги**</span><span class="sxs-lookup"><span data-stu-id="a8f7c-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="a8f7c-110">Если настраиваемые правила нормализации адресной книги в старой среды необходимо перенести настраиваемых правил пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="a8f7c-111">Если не были указаны пользователем правила нормализации адресной книги, вы не для переноса для службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="a8f7c-112">Правила нормализации по умолчанию для Скайп для Business Server 2019 такие же, как правила по умолчанию при установке прежних версий.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="a8f7c-113">Выполните процедуру, описанную далее в этом разделе перенос правил нормализации настраиваемая.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="a8f7c-114">Если организация использует удаленного управления звонками и настроенных правил нормализации адресной книги, необходимо выполнить процедуры в этом разделе прежде чем можно будет использовать удаленное управление звонками.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="a8f7c-115">Процедуры необходимо быть членом группы RTCUniversalServerAdmins или эквивалентные права.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="a8f7c-116">**Параметр UseNormalizationRules имеет значение False**</span><span class="sxs-lookup"><span data-stu-id="a8f7c-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="a8f7c-117">При установке значения для **UseNormalizationRules** значение False, чтобы пользователи могли использовать номера телефонов, как они определены в доменных службах Active Directory без необходимости Скайп для Business Server 2019 применения правил нормализации, необходимо задать \*\* UseNormalizationRules\*\* и параметры **IgnoreGenericRules** на True.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="a8f7c-118">Выполните процедуру, описанную далее в этом разделе для этих параметров на значение True.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="a8f7c-119">Перенос адресной книги настроенных правил нормализации</span><span class="sxs-lookup"><span data-stu-id="a8f7c-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="a8f7c-120">Найдите файл Company_Phone_Number_Normalization_Rules.txt в корне общей папки адресной книги и скопируйте его в корень общей папки адресной книги в вашей Скайп для пилотного пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a8f7c-121">Примеры правил нормализации адресной книги установленные ABS каталога используемого веб-компонент файла.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="a8f7c-122">— Это путь **$installedDriveLetter: \Program Files\Microsoft Скайп для Business Server 2019\Web Components\Address книги Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="a8f7c-123">Этот файл можно скопировать и переименован как **Company_Phone_Number_Normalization_Rules.txt** в корневой каталог адресной книги общей папки.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="a8f7c-124">Например, в адресной книге, совместно в **$serverX**путь будет аналогичен: \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="a8f7c-125">Используйте текстовый редактор, например "Блокнот", чтобы открыть файл Company_Phone_Number_Normalization_Rules.txt.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="a8f7c-126">Определенные типы записей не будет работать в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="a8f7c-127">Просмотрите файл для типов записей, описанного на этом шаге, при необходимости изменить и сохранить изменения в общую папку адресной книги в пилотном пуле.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="a8f7c-128">Строки, содержащие требуемые пробелов и знаков препинания причина правил нормализации к сбою, так как эти символы удаляются из строки, полученный правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="a8f7c-129">Если у вас есть строк, содержащих необходимые пробелов и знаков препинания, необходимо изменить строк.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="a8f7c-130">Например следующая строка приведет к сбою правила нормализации:</span><span class="sxs-lookup"><span data-stu-id="a8f7c-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="a8f7c-131">Следующая строка не приведет к сбою правила нормализации:</span><span class="sxs-lookup"><span data-stu-id="a8f7c-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="a8f7c-132">Чтобы задать UseNormalizationRules и IgnoreGenericRules на true</span><span class="sxs-lookup"><span data-stu-id="a8f7c-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="a8f7c-133">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп Microsoft для Business Server 2019**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a8f7c-134">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="a8f7c-134">Do one of the following:</span></span>

   - <span data-ttu-id="a8f7c-135">Если в развертывании имеется только Скайп для 2019 Business Server, выполните следующий командлет на глобальном уровне, чтобы изменить значения для **UseNormalizationRules** и **IgnoreGenericRules** на True:</span><span class="sxs-lookup"><span data-stu-id="a8f7c-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="a8f7c-136">Если развертывание включает сочетание Скайп Business Server 2019 и устаревшие установки, выполните следующий командлет и назначьте его для каждого Скайп для пула Business Server 2019 в топологии:</span><span class="sxs-lookup"><span data-stu-id="a8f7c-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="a8f7c-137">Дождитесь репликации хранилища централизованного управления будет выполнена для всех пулов.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="a8f7c-138">Измените файл правил нормализации телефонных, «Company_Phone_Number_Normalization_Rules.txt», для развертывания для очистки содержимого.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="a8f7c-139">Файл находится в файловом ресурсе каждого Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a8f7c-140">Если файл не существует, создайте пустой файл с именем «Company_Phone_Number_Normalization_Rules.txt».</span><span class="sxs-lookup"><span data-stu-id="a8f7c-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="a8f7c-141">Подождите несколько минут для всех пулов переднего плана не будут прочитаны новые файлы.</span><span class="sxs-lookup"><span data-stu-id="a8f7c-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="a8f7c-142">Выполните следующий командлет на каждом Скайп для Business Server 2019 пула в развертывании:</span><span class="sxs-lookup"><span data-stu-id="a8f7c-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


