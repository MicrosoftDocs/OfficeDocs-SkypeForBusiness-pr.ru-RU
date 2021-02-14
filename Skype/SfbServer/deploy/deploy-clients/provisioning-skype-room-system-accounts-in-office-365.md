---
title: Подготовка учетных записей системы комнат Skype в Microsoft 365 и Office 365
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
description: В этом разделе содержится информация о предоставлении учетных записей системы комнат Skype в Microsoft 365 или Office 365.
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820849"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Подготовка учетных записей системы комнат Skype в Microsoft 365 и Office 365
 
В этом разделе содержится информация о предоставлении учетных записей системы комнат Skype в Microsoft 365 или Office 365.
  
В следующем разделе описывается подготовка учетной записи системы комнат Skype.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Предварительные условия для Microsoft 365 и Office 365

Ваш сетевой клиент должен соответствовать следующим требованиям:
  
- План Microsoft 365 или Office 365 должен включать Skype для бизнеса Online (план 2) или Office 365 E1, E3 или E5. <br/>Подробные сведения о планах Skype для бизнеса Online см. в [описании службы Skype для бизнеса Online.](https://technet.microsoft.com/library/jj822172.aspx)
    
- В клиенте должна быть включена возможность работы со Skype для бизнеса.
    
- В клиенте должна быть включена exchange Online. 
    
- Удаленный администратор клиента должен иметь следующий доступ к PowerShell:
    
  - Удаленный доступ к PowerShell для Exchange
    
  - Удаленный доступ к PowerShell в Skype для бизнеса Online
    
  - Windows Azure active Directory для Windows PowerShell доступа к каталогам Microsoft 365 или Office 365
    
Для учетной записи комнат Skype требуется следующее лицензирование:
  
- Чтобы включить собрания Skype, необходима лицензия Skype для бизнеса Online (план 2) или Office 365 E1 или E3.
    
- Чтобы сделать комнату с возможностью Корпоративная голосовая связь, чтобы в нее можно было включить номер телефона, требуется Skype для бизнеса Online (план 2) с лицензией на телефонную систему или Office 365 E5 (1).
    
- Если вам требуются возможности телефонного звонка на собрании, вам потребуется лицензия на аудиоконференцию и телефонную систему.  Если вам требуются возможности телефонного звонка на собрании, вам потребуется план внутренних или внутренних и международных звонков. 
    
- Лицензия Exchange Online не требуется для учетной записи комнаты Skype, так как она должна быть настроена как учетная запись почтового ящика ресурса.
    
## <a name="provisioning-overview"></a>Общие сведения о подготовках

На следующей схеме представлен обзор потока предоставления учетной записи системы комнат Skype.
  
![Этапы предоставления системы комнат Skype](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Определение нового конференц-зала

Возможно, у вас уже есть почтовый ящик помещения ресурсов в Exchange, который предоставляет функцию планирования, или вы можете создать почтовый ящик ресурса в первый раз для упрощения развертывания системы комнат Skype. В любом случае необходимо определить учетную запись помещения, которая будет использоваться в клиенте. Разделы "Подготовка Exchange Online" и "Подготовка Skype для бизнеса" предоставляют руководство по обоим типам учетных записей. Например, предположим, что у вас есть две следующие комнаты, и вы хотите развернуть систему комнат Skype для обеих комнат:
  
- Существующая учетная запись почтового ящика ресурса: confrm1@contoso.onmicrosoft.com
    
- Новая учетная запись почтового ящика ресурса: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Подготовка Exchange Online

Сначала подключите Exchange Online PowerShell, следуя инструкциям в этой теме, подключите [к Exchange Online PowerShell.](https://go.microsoft.com/fwlink/p/?LinkId=396554)
  
Чтобы настроить существующую учетную запись почтового ящика помещения ресурсов для системы комнат Skype, в Exchange Online PowerShell запустите следующие команды:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Чтобы создать новую учетную запись почтового ящика ресурса Exchange для системы комнат Skype, в Exchange Online PowerShell запустите следующие команды:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Предыдущие команды позволяют настроить или создать новую учетную запись почтового ящика ресурса Exchange для использования системы комнат Skype, включив учетную запись.
  
После создания почтового ящика можно использовать Set-CalendarProcessing в Exchange Online PowerShell для настройки почтового ящика. Дополнительные сведения о шагах 3-6 в локальном развертывании с одним лесом

## <a name="assigning-a-skype-for-business-online-license"></a>Назначение лицензии Skype для бизнеса Online

Теперь вы можете назначить лицензию на Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3) с помощью портала администрирования Microsoft 365, как описано в описании назначения или удаления лицензий для [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) для бизнеса или лицензирования надстройки [Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)для бизнеса. 
  
После назначения лицензии для Skype для бизнеса Online вы сможете войти в систему и проверить, активна ли учетная запись, с помощью любого клиента Skype для бизнеса.
  
## <a name="skype-for-business-online-provisioning"></a>Подготовка Skype для бизнеса Online

После создания и включения учетной записи почтового ящика помещения ресурсов, как показано ранее, и лицензирования учетной записи Skype для бизнеса Online учетная запись будет синхронизироваться из леса Exchange Online с лесом Skype для бизнеса Online с помощью Windows Azure леса Active Directory. Для предоставления учетной записи системы комнат Skype в пуле Skype для бизнеса Online необходимо сделать следующее. Эти действия одинаковы как для существующей учетной записи почтового ящика ресурса, так и для вновь созданной учетной записи (confrm1 или confrm2), так как после включения в Exchange Online обе эти учетные записи будут синхронизированы со Skype для бизнеса Online таким же образом:
  
1. Создание удаленного сеанса PowerShell. Обратите внимание, что вам потребуется скачать модуль соединителю Skype для бизнеса Online и Microsoft Online Services Sign-In помощника и убедиться, что компьютер настроен. Дополнительные сведения [см.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)в этой Windows PowerShell.
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Чтобы включить учетную запись системы комнат Skype для Skype для бизнеса, запустите следующую команду:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Чтобы получить это свойство, вы можете получить адрес RegistrarPool, на котором находятся пользователи Skype для бизнеса, из одной из существующих учетных записей, используя следующую команду:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Многофакторная проверка подлинности (MFA) не поддерживается для учетных записей системы комнат Skype. 

## <a name="password-expiration"></a>Срок действия пароля

В Microsoft 365 или Office 365 политика срока действия паролей по умолчанию для всех учетных записей пользователей составляет 90 дней, если вы не настроите другую политику срока действия паролей. Для учетных записей системы комнат Skype можно выбрать параметр "Срок действия пароля никогда не истекает", вы можете сделать следующее.
  
1. Создайте сеанс Windows Azure Active Directory, используя учетные данные глобального администратора клиента.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Установите параметр "Срок действия пароля не истекает" для учетной записи системы комнат Skype, созданной ранее, с помощью следующей команды:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Дополнительные сведения [см.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)в этой Windows PowerShell.
  
## <a name="validate"></a>Проверка

Для проверки вы должны иметь возможность использовать любой клиент Skype для бизнеса, чтобы войти в созданную учетную запись.

