---
title: Перенос адресной книги
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Как правило, адресная книга переносится вместе с остальной частью топологии. Тем не менее, если вы настроили следующие действия в устаревшей среде, вам может потребоваться выполнить некоторые действия, выполняемые после миграции:'
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752841"
---
# <a name="migrate-address-book"></a><span data-ttu-id="ffba6-104">Перенос адресной книги</span><span class="sxs-lookup"><span data-stu-id="ffba6-104">Migrate Address Book</span></span>

<span data-ttu-id="ffba6-105">Как правило, адресная книга переносится вместе с остальной частью топологии.</span><span class="sxs-lookup"><span data-stu-id="ffba6-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="ffba6-106">Тем не менее, если вы настроили следующие действия в устаревшей среде, вам может потребоваться выполнить некоторые действия, выполняемые после миграции:</span><span class="sxs-lookup"><span data-stu-id="ffba6-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="ffba6-107">настроили правила нормализации адресной книги;</span><span class="sxs-lookup"><span data-stu-id="ffba6-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="ffba6-108">изменили значение по умолчанию параметра **UseNormalizationRules** на False.</span><span class="sxs-lookup"><span data-stu-id="ffba6-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="ffba6-109">**Правила нормализации адресной книги**</span><span class="sxs-lookup"><span data-stu-id="ffba6-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="ffba6-110">Если вы настроили правила нормализации адресных книг в устаревшей среде, необходимо перенести измененные правила в пилотный пул.</span><span class="sxs-lookup"><span data-stu-id="ffba6-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="ffba6-111">Если вы не настраивали правила нормализации адресной книги, то ничего переносить не требуется.</span><span class="sxs-lookup"><span data-stu-id="ffba6-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="ffba6-112">Правила нормализации по умолчанию для Skype для бизнеса Server 2019 совпадают с правилами по умолчанию для установки прежних версий.</span><span class="sxs-lookup"><span data-stu-id="ffba6-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="ffba6-113">Чтобы перенести настроенные правила нормализации, выполните инструкции, приведенные далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ffba6-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="ffba6-p104">Если в вашей организации используется удаленное управление звонками и вы настроили правила нормализации адресной книги, то прежде чем использовать удаленное управление звонками, вам нужно выполнить инструкции, приведенные в этом разделе. Для их выполнения необходимо быть членом группы RTCUniversalServerAdmins или иметь аналогичные права.</span><span class="sxs-lookup"><span data-stu-id="ffba6-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="ffba6-116">**Параметр UseNormalizationRules со значением False**</span><span class="sxs-lookup"><span data-stu-id="ffba6-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="ffba6-117">Если задать для параметра **UseNormalizationRules** значение false, чтобы пользователи могли использовать номера телефонов в соответствии с их определением в доменных службах Active Directory без применения правил нормализации в Skype для бизнеса Server 2019, необходимо задать для параметров **UseNormalizationRules** и **IgnoreGenericRules** значение true.</span><span class="sxs-lookup"><span data-stu-id="ffba6-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="ffba6-118">Для этого выполните инструкции, приведенные далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ffba6-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="ffba6-119">Перенос настроенных правил нормализации адресной книги</span><span class="sxs-lookup"><span data-stu-id="ffba6-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="ffba6-120">Найдите файл Company_Phone_Number_Normalization_Rules.txt в корне общей папки адресной книги и скопируйте его в корневую папку адресной книги в пилотном пуле Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ffba6-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ffba6-121">Образцы правил нормализации адресной книги установлены в каталоге, содержащем файлы веб-компонента службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="ffba6-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="ffba6-122">Путь **$installedDriveLetter: \Program Files\Microsoft Skype для бизнеса Server 2019 \ Web Компонентс\аддресс Book филес\филес\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="ffba6-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="ffba6-123">Этот файл можно скопировать и переименовать как **Company_Phone_Number_Normalization_Rules.txt** в корневой каталог общей папки адресной книги.</span><span class="sxs-lookup"><span data-stu-id="ffba6-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="ffba6-124">Например, адресная книга предоставляется в **$serverX**, путь будет выглядеть следующим образом: \*\* \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="ffba6-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="ffba6-125">Откройте файл Company_Phone_Number_Normalization_Rules.txt с помощью текстового редактора, например Блокнота.</span><span class="sxs-lookup"><span data-stu-id="ffba6-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="ffba6-126">Некоторые типы записей не будут правильно работать в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ffba6-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="ffba6-127">Просмотрите файл, чтобы найти записи такого типа, измените их требуемым образом и сохраните изменения в общей папке адресной книги в пилотном пуле.</span><span class="sxs-lookup"><span data-stu-id="ffba6-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="ffba6-p108">Строки, содержащие обязательный пробел или знак пунктуации, приведут к сбою правила нормализации, поскольку эти символы удаляются из строки при ее вводе в правило. Если у вас есть строки с обязательным пробелом или знаком пунктуации, их нужно изменить. Например, следующая строка приведет к сбою правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="ffba6-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="ffba6-131">Следующая строка не приведет к сбою правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="ffba6-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="ffba6-132">Задание значения True для параметров UseNormalizationRules и IgnoreGenericRules</span><span class="sxs-lookup"><span data-stu-id="ffba6-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="ffba6-133">Запустите командную консоль Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft Skype для бизнеса Server 2019**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="ffba6-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ffba6-134">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="ffba6-134">Do one of the following:</span></span>

   - <span data-ttu-id="ffba6-135">Если в развертывании есть только Skype для бизнеса Server 2019, выполните следующий командлет на глобальном уровне, чтобы изменить значения для **UseNormalizationRules** и **IgnoreGenericRules** на true:</span><span class="sxs-lookup"><span data-stu-id="ffba6-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="ffba6-136">Если в развертывании есть сочетание Skype для бизнеса Server 2019 и устаревшей установки, выполните следующий командлет и назначьте его каждому пулу Skype для бизнеса Server 2019 в топологии:</span><span class="sxs-lookup"><span data-stu-id="ffba6-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="ffba6-137">Дождитесь, пока репликация центрального хранилища управления не будет выполняться во всех пулах.</span><span class="sxs-lookup"><span data-stu-id="ffba6-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="ffba6-138">Очистите содержимое файла правил нормализации телефонов (Company_Phone_Number_Normalization_Rules.txt) для развертывания.</span><span class="sxs-lookup"><span data-stu-id="ffba6-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="ffba6-139">Файл находится на общем файловом ресурсе каждого пула Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ffba6-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ffba6-140">Если файл отсутствует, создайте пустой файл с именем Company_Phone_Number_Normalization_Rules.txt.</span><span class="sxs-lookup"><span data-stu-id="ffba6-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="ffba6-141">Подождите несколько минут, пока для всех интерфейсных пулов не будут прочитаны новые файлы.</span><span class="sxs-lookup"><span data-stu-id="ffba6-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="ffba6-142">Выполните следующий командлет на каждом пуле Skype для бизнеса Server 2019 в развертывании:</span><span class="sxs-lookup"><span data-stu-id="ffba6-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


