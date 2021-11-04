---
title: Подготовка Skype учетных записей системы номеров в Microsoft 365 и Office 365
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Ознакомьтесь с этой темой, чтобы узнать о Skype учетных записей системы номеров в Microsoft 365 или Office 365.
ms.openlocfilehash: 1f4262453735baa08e16e7da03909e48ef12f4ff
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758121"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Подготовка Skype учетных записей системы номеров в Microsoft 365 и Office 365
 
Ознакомьтесь с этой темой, чтобы узнать о Skype учетных записей системы номеров в Microsoft 365 или Office 365.
  
В следующем разделе Skype подготовка учетной записи системы номеров.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365 и Office 365 условия

Ваш онлайн-клиент должен соответствовать следующим требованиям:
  
- План Microsoft 365 или Office 365 должен включать Skype для бизнеса Online Plan 2 или Office 365 E1, E3 или E5. <br/>Подробные сведения о Skype для бизнеса Online Plans см. в [Skype для бизнеса Описание службы.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)
    
- Клиент должен иметь возможность конференциинга с Skype для бизнеса включенной.
    
- Клиент должен иметь Exchange Online включен. 
    
- Удаленный администратор клиента должен иметь следующий доступ к PowerShell:
    
  - Exchange Удаленный доступ к PowerShell
    
  - Skype для бизнеса Доступ к удаленной сети PowerShell
    
  - Windows Azure Active Directory модуль для Windows PowerShell доступа Microsoft 365 или Office 365 каталога
    
Для учетной Skype Room требуется следующее лицензирование:
  
- Для Skype для бизнеса online Plan 2 или Office 365 E1 или E3 требуется лицензия на Skype собраний.
    
- Чтобы уместить комнату с Корпоративная голосовая связь для включения номера телефона, необходимо Skype для бизнеса Online Plan 2 с телефонная система лицензией или Office 365 E5 (1).
    
- Если вам нужны возможности для набора номера на собрании, вам потребуется аудиоконференция и телефонная система лицензия.  Если вам необходимы возможности для телефонного звонка на собрании, вам потребуется внутренний или внутренний и международный план звонков. 
    
- Лицензия Exchange Online не требуется для учетной записи Skype Room, так как учетная запись должна быть настроена как учетная запись почтового ящика ресурса.
    
## <a name="provisioning-overview"></a>Обзор подготовка

На следующей схеме представлен обзор потока Skype учетной записи системы номеров.
  
![Skype Этапы подготовка системы номеров.](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Определение нового конференц-зала

Возможно, у вас уже есть почтовый ящик комнаты ресурсов в Exchange, который предоставляет функцию планирования, или вы можете создать почтовый ящик ресурса в первый раз для облегчения развертывания Skype системы номеров. В любом случае необходимо определить учетную запись комнаты, которая будет использоваться в клиенте. Разделы Exchange Online и Skype для бизнеса положения предоставляют рекомендации по обоим типам учетных записей. Например, предположим, что у вас есть следующие две комнаты, и вы хотите развернуть Skype для обеих комнат:
  
- Существующая учетная запись почтовых ящиков ресурса: confrm1@contoso.onmicrosoft.com
    
- Новая учетная запись почтового ящика ресурса: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online подготовка

Во-первых, подключите Exchange Online PowerShell, следуя инструкциям в этой теме, Подключение [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
Чтобы установить существующую учетную запись почтового ящика комнаты ресурсов для Skype Room System, запустите следующие команды в Exchange Online PowerShell:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Чтобы создать новую учетную запись Exchange ресурса для Skype Room System, запустите следующие команды в Exchange Online PowerShell:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Предыдущие команды создали или создали новую учетную запись Exchange ресурса для Skype системы номеров, включив учетную запись.
  
После создания почтового ящика можно использовать Set-CalendarProcessing в Exchange Online PowerShell для настройки почтового ящика. Дополнительные сведения по ссылкам на этапы 3-6 в локальном развертывании "Единый лес"

## <a name="assigning-a-skype-for-business-online-license"></a>Назначение лицензии Skype для бизнеса Online

Теперь вы можете назначить лицензию Skype для бизнеса Online (Plan 2) или Skype для бизнеса Online (Plan 3) с помощью [](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) портала администрирования Microsoft 365, как описано в описании Назначение или удаление лицензий для Microsoft 365 для бизнеса или Skype для бизнеса лицензирования надстройки [.](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7) 
  
После назначения лицензии для Skype для бизнеса Online вы сможете войти и проверить, активна ли учетная запись с помощью Skype для бизнеса клиента.
  
## <a name="skype-for-business-online-provisioning"></a>Skype для бизнеса Подготовка в Интернете

После создания и включения учетной записи почтового ящика комнаты ресурсов, как показано ранее, и вы лицензируете учетную запись для Skype Для бизнеса Online, учетная запись синхронизируется с лесом Exchange Online до Skype для бизнеса Online с помощью Windows Azure Active Directory леса. Для предоставления учетной записи Skype в пуле Skype для бизнеса Online требуются следующие действия. Эти действия одинаковы как для существующей учетной записи почтового ящика ресурса, так и для вновь созданной учетной записи (confrm1 или confrm2), так как после включения в Exchange Online обе эти учетные записи будут синхронизированы с Skype для бизнеса Online таким же образом:
  
1. Создание сеанса Удаленной PowerShell. Обратите внимание, что вам потребуется [скачать Teams PowerShell.](/microsoftteams/teams-powershell-install)
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. Чтобы включить учетную запись Skype для Skype для бизнеса, запустите следующую команду:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Вы можете получить адрес RegistrarPool, где Skype для бизнеса пользователи находятся в одной из существующих учетных записей, используя следующую команду, чтобы вернуть это свойство:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Многофакторная проверка подлинности (MFA) не поддерживается для Skype учетных записей системы номеров. 

## <a name="password-expiration"></a>Срок действия пароля

В Microsoft 365 или Office 365 срок действия пароля по умолчанию для всех учетных записей пользователей составляет 90 дней, если не настроить другую политику истечения пароля. Для Skype учетных записей системы номеров можно выбрать параметр Password, который никогда не истекает, с помощью следующих действий.
  
1. Создание сеанса Windows Azure Active Directory с помощью учетных данных глобального администратора клиента.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Настройка параметра Password никогда не истекает для учетной записи Skype комнатной системы, созданной ранее с помощью следующей команды:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Дополнительные сведения см. [в дополнительных сведениях о настройках](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)компьютера для Windows PowerShell.
  
## <a name="validate"></a>Проверка

Для проверки необходимо использовать любой клиент Skype для бизнеса для регистрации в созданной учетной записи.