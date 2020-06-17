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
# <a name="migrate-address-book"></a>Перенос адресной книги

Как правило, адресная книга переносится вместе с остальной частью топологии. Тем не менее, если вы настроили следующие действия в устаревшей среде, вам может потребоваться выполнить некоторые действия, выполняемые после миграции: 

- настроили правила нормализации адресной книги;

- изменили значение по умолчанию параметра **UseNormalizationRules** на False. 


 **Правила нормализации адресной книги**

Если вы настроили правила нормализации адресных книг в устаревшей среде, необходимо перенести измененные правила в пилотный пул. Если вы не настраивали правила нормализации адресной книги, то ничего переносить не требуется. Правила нормализации по умолчанию для Skype для бизнеса Server 2019 совпадают с правилами по умолчанию для установки прежних версий. Чтобы перенести настроенные правила нормализации, выполните инструкции, приведенные далее в этом разделе.

> [!NOTE]
> If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights. 

 **Параметр UseNormalizationRules со значением False**

Если задать для параметра **UseNormalizationRules** значение false, чтобы пользователи могли использовать номера телефонов в соответствии с их определением в доменных службах Active Directory без применения правил нормализации в Skype для бизнеса Server 2019, необходимо задать для параметров **UseNormalizationRules** и **IgnoreGenericRules** значение true. Для этого выполните инструкции, приведенные далее в этом разделе. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Перенос настроенных правил нормализации адресной книги

1. Найдите файл Company_Phone_Number_Normalization_Rules.txt в корне общей папки адресной книги и скопируйте его в корневую папку адресной книги в пилотном пуле Skype для бизнеса Server 2019.

    > [!NOTE]
    > Образцы правил нормализации адресной книги установлены в каталоге, содержащем файлы веб-компонента службы адресной книги. Путь **$installedDriveLetter: \Program Files\Microsoft Skype для бизнеса Server 2019 \ Web Компонентс\аддресс Book филес\филес\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Этот файл можно скопировать и переименовать как **Company_Phone_Number_Normalization_Rules.txt** в корневой каталог общей папки адресной книги. Например, адресная книга предоставляется в **$serverX**, путь будет выглядеть следующим образом: ** \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Откройте файл Company_Phone_Number_Normalization_Rules.txt с помощью текстового редактора, например Блокнота.

3. Некоторые типы записей не будут правильно работать в Skype для бизнеса Server 2019. Просмотрите файл, чтобы найти записи такого типа, измените их требуемым образом и сохраните изменения в общей папке адресной книги в пилотном пуле.

    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    Следующая строка не приведет к сбою правила нормализации.

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Задание значения True для параметров UseNormalizationRules и IgnoreGenericRules

1. Запустите командную консоль Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft Skype для бизнеса Server 2019**и щелкните **Командная консоль Skype для бизнеса Server**.

2. Выполните одно из указанных ниже действий.

   - Если в развертывании есть только Skype для бизнеса Server 2019, выполните следующий командлет на глобальном уровне, чтобы изменить значения для **UseNormalizationRules** и **IgnoreGenericRules** на true: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Если в развертывании есть сочетание Skype для бизнеса Server 2019 и устаревшей установки, выполните следующий командлет и назначьте его каждому пулу Skype для бизнеса Server 2019 в топологии:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Дождитесь, пока репликация центрального хранилища управления не будет выполняться во всех пулах.

4. Очистите содержимое файла правил нормализации телефонов (Company_Phone_Number_Normalization_Rules.txt) для развертывания. Файл находится на общем файловом ресурсе каждого пула Skype для бизнеса Server 2019. Если файл отсутствует, создайте пустой файл с именем Company_Phone_Number_Normalization_Rules.txt.

5. Подождите несколько минут, пока для всех интерфейсных пулов не будут прочитаны новые файлы.

6. Выполните следующий командлет на каждом пуле Skype для бизнеса Server 2019 в развертывании:

   ```PowerShell
   Update-CsAddressBook
   ```


