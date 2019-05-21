---
title: Перенос адресной книги
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В общем случае адресная книга переносится вместе с оставшейся частью вашей топологии. Однако вам может потребоваться выполнить некоторые действия после миграции, если в устаревшей среде были настроены указанные ниже компоненты.
ms.openlocfilehash: 4263ae5bff60859cc9606a3683a3a03b0d2d4c35
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307121"
---
# <a name="migrate-address-book"></a><span data-ttu-id="e11a2-104">Перенос адресной книги</span><span class="sxs-lookup"><span data-stu-id="e11a2-104">Migrate Address Book</span></span>

<span data-ttu-id="e11a2-105">В общем случае адресная книга переносится вместе с оставшейся частью вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="e11a2-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="e11a2-106">Однако вам может потребоваться выполнить некоторые действия после миграции, если в устаревшей среде были настроены указанные ниже компоненты.</span><span class="sxs-lookup"><span data-stu-id="e11a2-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="e11a2-107">Настроены правила нормализации адресных книг.</span><span class="sxs-lookup"><span data-stu-id="e11a2-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="e11a2-108">Изменение значения по умолчанию для параметра **усенормализатионрулес** на false.</span><span class="sxs-lookup"><span data-stu-id="e11a2-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="e11a2-109">**Правила нормализации адресных книг**</span><span class="sxs-lookup"><span data-stu-id="e11a2-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="e11a2-110">Если вы настроили правила нормализации адресных книг в устаревшей среде, необходимо перенести настроенные правила в свой проект пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="e11a2-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="e11a2-111">Если вы не настраиваете правила нормализации адресных книг, вы не можете выполнить миграцию для службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="e11a2-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="e11a2-112">Правила нормализации по умолчанию для Skype для бизнеса Server 2019 совпадают с правилами по умолчанию для установленной версии.</span><span class="sxs-lookup"><span data-stu-id="e11a2-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="e11a2-113">Выполните действия, описанные ниже в этом разделе, чтобы перенести настраиваемые правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="e11a2-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="e11a2-114">Если в вашей организации используется удаленное управление звонками и настроены правила нормализации адресных книг, необходимо выполнить описанные ниже действия, прежде чем можно будет использовать удаленное управление звонками.</span><span class="sxs-lookup"><span data-stu-id="e11a2-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="e11a2-115">Процедура требует членства в группе Рткуниверсалсерверадминс или эквивалентных прав.</span><span class="sxs-lookup"><span data-stu-id="e11a2-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="e11a2-116">**Для Усенормализатионрулес задано значение false**</span><span class="sxs-lookup"><span data-stu-id="e11a2-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="e11a2-117">Если задать для **усенормализатионрулес** значение false, чтобы пользователи могли использовать номера телефонов, определенные в доменных службах Active Directory, не имея в Skype для бизнеса Server 2019 правила нормализации, необходимо задать \*\*для параметра \*\*Для параметров усенормализатионрулес и **Игнореженерикрулес** значение true.</span><span class="sxs-lookup"><span data-stu-id="e11a2-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="e11a2-118">Выполните действия, описанные ниже в этом разделе, чтобы установить для этих параметров значение true.</span><span class="sxs-lookup"><span data-stu-id="e11a2-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="e11a2-119">Миграция настроенных правил нормализации в адресной книге</span><span class="sxs-lookup"><span data-stu-id="e11a2-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="e11a2-120">Найдите файл Компани_фоне_нумбер_нормализатион_рулес. txt в корне общей папки адресной книги и скопируйте его в корневой каталог общей папки адресной книги в корпоративном пуле Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e11a2-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e11a2-121">Примеры правил нормализации адресных книг установлены в каталог файлов веб-компонентов ABS.</span><span class="sxs-lookup"><span data-stu-id="e11a2-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="e11a2-122">Путь — это **$installedDriveLetter: \Program Files\Microsoft Компонентс\аддресс Book Филес\филес\ сампле_компани_фоне_нумбер_нормализатион_рулес. txt в Skype для бизнеса Server 2019**.</span><span class="sxs-lookup"><span data-stu-id="e11a2-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="e11a2-123">Этот файл можно скопировать и переименовать как **компани_фоне_нумбер_нормализатион_рулес. txt** в корневой каталог общей папки адресной книги.</span><span class="sxs-lookup"><span data-stu-id="e11a2-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="e11a2-124">Например, адресная книга, доступная в **$serverX**, будет выглядеть примерно так: \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="e11a2-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="e11a2-125">Откройте файл Компани_фоне_нумбер_нормализатион_рулес. txt с помощью текстового редактора (например, блокнота).</span><span class="sxs-lookup"><span data-stu-id="e11a2-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="e11a2-126">Некоторые типы записей не будут правильно работать в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e11a2-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="e11a2-127">Просмотрите файл на предмет типов записей, описанных в этом шаге, внесите необходимые изменения и сохраните изменения в общей папке адресной книги в вашем пилотном пуле.</span><span class="sxs-lookup"><span data-stu-id="e11a2-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="e11a2-128">Строки, содержащие требуемый пробел или знаки препинания, приводят к сбою правил нормализации, так как эти символы удаляются из строки, вводимой в правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="e11a2-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="e11a2-129">Если у вас есть строки, содержащие необходимые пробелы или знаки препинания, необходимо изменить строки.</span><span class="sxs-lookup"><span data-stu-id="e11a2-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="e11a2-130">Например, следующая строка может привести к сбою правила нормализации:</span><span class="sxs-lookup"><span data-stu-id="e11a2-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="e11a2-131">Следующая строка не приводила к сбою правила нормализации:</span><span class="sxs-lookup"><span data-stu-id="e11a2-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="e11a2-132">Чтобы установить для Усенормализатионрулес и Игнореженерикрулес значение true,</span><span class="sxs-lookup"><span data-stu-id="e11a2-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="e11a2-133">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Skype для бизнеса Server 2019**, а затем — **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="e11a2-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e11a2-134">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e11a2-134">Do one of the following:</span></span>

   - <span data-ttu-id="e11a2-135">Если в развертывании есть только Skype для бизнеса Server 2019, выполните следующий командлет на глобальном уровне, чтобы изменить значения **усенормализатионрулес** и **игнореженерикрулес** на true:</span><span class="sxs-lookup"><span data-stu-id="e11a2-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="e11a2-136">Если в развертывании есть сочетание Skype для бизнеса Server 2019 и устаревшая установка, запустите следующий командлет и назначьте его каждому из пулов Skype для Business Server 2019 в топологии.</span><span class="sxs-lookup"><span data-stu-id="e11a2-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="e11a2-137">Дождитесь, когда репликация хранилища центрального управления будет выполняться на всех пулах.</span><span class="sxs-lookup"><span data-stu-id="e11a2-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="e11a2-138">Измените файл правил нормализации телефона в разделе "Компани_фоне_нумбер_нормализатион_рулес. txt" для развертывания, чтобы очистить содержимое.</span><span class="sxs-lookup"><span data-stu-id="e11a2-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="e11a2-139">Этот файл находится в общей папке каждого пула 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e11a2-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e11a2-140">Если файл не отображается, создайте пустой файл с именем "Компани_фоне_нумбер_нормализатион_рулес. txt".</span><span class="sxs-lookup"><span data-stu-id="e11a2-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="e11a2-141">Подождите несколько минут, пока все клиентские пулы смогут прочитать новые файлы.</span><span class="sxs-lookup"><span data-stu-id="e11a2-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="e11a2-142">Выполните следующий командлет на каждом пуле 2019 для Business Server в среде Skype.</span><span class="sxs-lookup"><span data-stu-id="e11a2-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


