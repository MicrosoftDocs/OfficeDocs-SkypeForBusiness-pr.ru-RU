---
title: Подготовка учетных записей skype Room System в Microsoft 365 и Office 365
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Ознакомьтесь с этой темой, чтобы узнать об обеспечении учетных записей skype Room System в Microsoft 365 или Office 365.
ms.openlocfilehash: 94390effb246a37745d797289c1146ed3d347604
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093523"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Подготовка учетных записей skype Room System в Microsoft 365 и Office 365
 
Ознакомьтесь с этой темой, чтобы узнать об обеспечении учетных записей skype Room System в Microsoft 365 или Office 365.
  
В следующем разделе описывается подготовка учетной записи Skype Room System.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Предварительные условия Microsoft 365 и Office 365

Ваш онлайн-клиент должен соответствовать следующим требованиям:
  
- План Microsoft 365 или Office 365 должен включать Skype для бизнеса Online Plan 2 или Office 365 E1, E3 или E5. <br/>Подробные сведения о планах Skype для бизнеса в Интернете см. в описании [службы Skype для бизнеса Online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)
    
- Клиент должен иметь возможность ведения телефонных разговоров с поддержкой Skype для бизнеса.
    
- У клиента должна быть включена Exchange Online. 
    
- Удаленный администратор клиента должен иметь следующий доступ к PowerShell:
    
  - Удаленный доступ к PowerShell Exchange
    
  - Доступ к удаленной powerShell Skype для бизнеса в Интернете
    
  - Windows Azure Active Directory Module для Windows PowerShell доступа к каталогам Microsoft 365 или Office 365
    
Для учетной записи Skype Room требуется следующее лицензирование:
  
- Чтобы включить собрания Skype для бизнеса, требуется лицензия Skype для бизнеса Online Plan 2 или Office 365 E1 или E3.
    
- Чтобы иметь право на доступ к Корпоративная голосовая связь, чтобы номер можно было включить с номером телефона, требуется Skype для бизнеса Online Plan 2 с лицензией системы телефонов или Office 365 E5 (1).
    
- Если вам нужны возможности для набора номера на собрании, вам потребуется лицензия на аудиоконференцию и телефонную систему.  Если вам необходимы возможности для телефонного звонка на собрании, вам потребуется внутренний или внутренний и международный план звонков. 
    
- Лицензия Exchange Online не требуется для учетной записи Skype Room, так как учетная запись должна быть настроена как учетная запись почтового ящика ресурса.
    
## <a name="provisioning-overview"></a>Обзор подготовка

На следующей схеме представлен обзор потока подготовка учетной записи skype Room System.
  
![Шаги по обеспечению системы skype Room](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Определение нового конференц-зала

Возможно, у вас уже есть почтовый ящик комнаты ресурсов в Exchange, который предоставляет функцию планирования, или вы можете создать почтовый ящик ресурса впервые для облегчения развертывания системы Skype Room System. В любом случае необходимо определить учетную запись комнаты, которая будет использоваться в клиенте. Разделы Exchange Online Provision и Skype for Business Provision предоставляют рекомендации по обоим типам учетных записей. Например, предположим, что у вас есть следующие две комнаты, и вы хотите развернуть систему номеров Skype для обоих из них:
  
- Существующая учетная запись почтовых ящиков ресурса: confrm1@contoso.onmicrosoft.com
    
- Новая учетная запись почтового ящика ресурса: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Подготовка Exchange Online

Во-первых, подключите к Exchange Online PowerShell, следуя инструкциям в этой теме, [подключите к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
Чтобы установить существующую учетную запись почтового ящика комнаты ресурсов для системы номеров Skype, запустите следующие команды в Exchange Online PowerShell:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Чтобы создать новую учетную запись почтового ящика ресурсов Exchange для Системы номеров Skype, запустите следующие команды в Exchange Online PowerShell:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Предыдущие команды создали или создали новую учетную запись почтового ящика ресурсов Exchange для использования системы skype Room System, включив учетную запись.
  
После создания почтового ящика можно использовать Set-CalendarProcessing в Exchange Online PowerShell для настройки почтового ящика. Дополнительные сведения по ссылкам на этапы 3-6 в локальном развертывании "Единый лес"

## <a name="assigning-a-skype-for-business-online-license"></a>Назначение лицензии Skype для бизнеса Online

Теперь вы можете назначить лицензию Skype для бизнеса Online (План 2) или Skype для бизнеса Online (План 3) с помощью административного портала Microsoft 365, как описано в описании Назначение или удаление лицензий для [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) для бизнеса или в [лицензировании](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)надстройки Skype для бизнеса . 
  
После назначения лицензии для Skype для бизнеса Online вы сможете войти и проверить, активна ли учетная запись с помощью любого клиента Skype для бизнеса.
  
## <a name="skype-for-business-online-provisioning"></a>Подготовка Skype для бизнеса в Интернете

После создания и включения учетной записи почтового ящика комнаты ресурсов, как показано ранее, и вы лицензируете учетную запись Skype для бизнеса Online, учетная запись синхронизируется с лесом Exchange Online до леса Skype для бизнеса Online с помощью леса Windows Azure Active Directory. Для предоставления учетной записи Skype Room System в пуле Skype для бизнеса Online необходимы следующие действия. Эти действия одинаковы как для существующей учетной записи почтового ящика ресурса, так и для вновь созданной учетной записи (confrm1 или confrm2), так как после включения в Exchange Online обе эти учетные записи будут синхронизированы с Skype для бизнеса Online таким же образом:
  
1. Создание сеанса Удаленной PowerShell. Обратите внимание, что вам потребуется скачать [модуль Teams PowerShell.](/microsoftteams/teams-powershell-install)
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. Чтобы включить учетную запись Skype Room System для Skype для бизнеса, запустите следующую команду:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Вы можете получить адрес RegistrarPool, где ваши пользователи Skype для бизнеса находятся в одной из существующих учетных записей, используя следующую команду, чтобы вернуть это свойство:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Многофакторная проверка подлинности (MFA) не поддерживается для учетных записей skype Room System. 

## <a name="password-expiration"></a>Срок действия пароля

В Microsoft 365 или Office 365 политика истечения срока действия пароля по умолчанию для всех учетных записей пользователей составляет 90 дней, если не настроить другую политику истечения срока действия пароля. Для учетных записей системы номеров Skype можно выбрать параметр Password, который никогда не истекает с помощью следующих действий.
  
1. Создайте сеанс Windows Azure Active Directory с помощью учетных данных глобального администратора клиента.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Настройка параметра Password никогда не истекает для учетной записи комнаты Skype Room System, созданной ранее с помощью следующей команды:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Дополнительные сведения см. в [Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="validate"></a>Проверка

Для проверки необходимо использовать любой клиент Skype для бизнеса, чтобы войти в созданную учетную запись.