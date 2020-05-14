---
title: Подготовка учетных записей системы комнат Skype в Microsoft 365 и Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: В этом разделе рассказывается о подготовке учетных записей системы комнат Skype в Microsoft 365 или Office 365.
ms.openlocfilehash: dd79081c690863a5851295ab48a950b3f7af66af
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221853"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Подготовка учетных записей системы комнат Skype в Microsoft 365 и Office 365
 
В этом разделе рассказывается о подготовке учетных записей системы комнат Skype в Microsoft 365 или Office 365.
  
В следующем разделе рассматривается подготовка учетных записей системы комнат Skype.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Предварительные требования для Microsoft 365 и Office 365

Ваш клиент сети должен отвечать следующим требованиям:
  
- План Microsoft 365 или Office 365 должен включать Skype для бизнеса Online (план 2) или Office 365 E1, E3 или в. <br/>Подробнее о планах Skype для бизнеса Online можно узнать в статье [Описание службы Skype для бизнеса Online](https://technet.microsoft.com/library/jj822172.aspx).
    
- У вашего клиента должна быть возможность конференц-связи с включенной поддержкой Skype для бизнеса.
    
- У клиента должен быть включен Exchange Online. 
    
- Удаленный администратор клиента должен иметь следующий доступ к PowerShell:
    
  - Удаленный доступ PowerShell к Exchange
    
  - Доступ к удаленной оболочке PowerShell в Skype для бизнеса Online
    
  - Модуль Windows Azure Active Directory для Windows PowerShell для доступа к Microsoft 365 или Office 365 доступ к каталогу
    
Для учетной записи комнаты Skype необходимо следующее лицензирование:
  
- Для включения собраний Skype требуется лицензия Skype для бизнеса Online (план 2) или Office 365 E1 или E3.
    
- Чтобы обеспечить доступ к комнате с помощью корпоративной голосовой связи, чтобы комната могла быть включена с номером телефона, необходимо использовать Skype для бизнеса Online (план 2) с лицензией на телефонную систему или Office 365 (1).
    
- Если вам потребуются возможности телефонного подключения к собранию, вам потребуется позвонить на аудио-и видеоконференции.  Если вам требуется возможность исходящих вызовов из собрания, вам потребуется внутренний или внутренний и Международный план звонков. 
    
- Для учетной записи комнаты Skype не требуется лицензия на Exchange Online, так как эта учетная запись должна быть настроена как учетная запись почтового ящика ресурса.
    
## <a name="provisioning-overview"></a>Общие сведения о подготовке

На следующей схеме представлен обзор процесса подготовки учетной записи системы комнат Skype.
  
![Этапы подготовки системы комнат Skype](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Определение новой конференц-зала

Возможно, у вас уже есть почтовый ящик помещения ресурсов в Exchange, который предоставляет функцию планирования, или вы можете создать почтовый ящик ресурса, чтобы упростить развертывание системы комнат Skype. В любом случае необходимо указать учетную запись комнаты, которая будет использоваться в клиенте. В разделах подготовки Exchange Online и Skype для бизнеса представлены рекомендации для обоих типов учетных записей. Например, предположим, что у вас есть две следующие комнаты, и вы хотите развернуть систему комнат Skype для обоих из них:
  
- Существующая учетная запись почтового ящика ресурса: confrm1@contoso.onmicrosoft.com
    
- Новая учетная запись почтового ящика ресурса: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Подготовка Exchange Online

Сначала подключитесь к Exchange Online PowerShell, выполнив инструкции, приведенные в этом разделе, [подключитесь к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Чтобы задать существующую учетную запись почтового ящика для комнаты ресурсов для системы комнат Skype, выполните следующие команды в Exchange Online PowerShell:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Чтобы создать новую учетную запись почтового ящика ресурсов Exchange для системы комнат Skype, выполните следующие команды в Exchange Online PowerShell:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Предыдущие команды настраивают или создают новую учетную запись почтового ящика ресурса Exchange для использования системы комнат Skype, поддерживая учетную запись.
  
После создания почтового ящика можно использовать командлет Set-CalendarProcessing в Exchange Online PowerShell для настройки почтового ящика. Для получения дополнительных сведений обратитесь к разделу 3 – 6 в разделе Локальные развертывания одного леса.

## <a name="assigning-a-skype-for-business-online-license"></a>Назначение лицензии Skype для бизнеса Online

Теперь вы можете назначить лицензию Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3) с помощью административного портала Microsoft 365, как описано в [статье назначение и удаление лицензий для microsoft 365 для бизнеса](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) или в [лицензии на надстройку Skype для бизнеса](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
После назначения лицензии для Skype для бизнеса Online вы сможете войти в систему и проверить, активна ли эта учетная запись с помощью любого клиента Skype для бизнеса.
  
## <a name="skype-for-business-online-provisioning"></a>Подготовка к работе в Skype для бизнеса Online

После создания и включения учетной записи почтового ящика для помещения в ресурс, как показано выше, и лицензирования учетной записи для Skype для бизнеса Online учетная запись будет синхронизироваться с лесом Exchange Online в лесу Skype для бизнеса Online с помощью леса Windows Azure Active Directory. Для подготовки учетной записи системы комнат Skype в пуле Skype для бизнеса Online необходимо выполнить следующие действия. Эти действия одинаковы для существующей учетной записи почтового ящика ресурса или только что созданной учетной записи (confrm1 или confrm2), так как после включения в Exchange Online обе эти учетные записи будут синхронизированы с Skype для бизнеса Online аналогичным образом:
  
1. Создайте удаленный сеанс PowerShell. Обратите внимание, что вам потребуется скачать модуль соединителя Skype для бизнеса Online и помощник по входу в Microsoft Online Services и проверить, настроен ли компьютер. Для получения дополнительных сведений ознакомьтесь со статьей [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Чтобы включить учетную запись системы комнат Skype для Skype для бизнеса, выполните следующую команду:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Вы можете получить адрес RegistrarPool, на котором пользователи Skype для бизнеса находятся из одной из существующих учетных записей, выполнив следующую команду, чтобы возвратить это свойство:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Многофакторная проверка подлинности (MFA) не поддерживается для учетных записей системы комнат Skype. 

## <a name="password-expiration"></a>Срок действия пароля

В Microsoft 365 или Office 365 политика истечения срока действия паролей по умолчанию для всех учетных записей пользователей составляет 90 дней, если не настроена другая политика истечения срока действия пароля. Для учетных записей системы комнат Skype можно выбрать параметр срок действия пароля не ограничен, выполнив указанные ниже действия.
  
1. Создайте сеанс Windows Azure Active Directory с помощью учетных данных глобального администратора клиента.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Для учетной записи комнаты системы комнат Skype, созданной ранее с помощью следующей команды, установите параметр пароль не ограничен сроком действия.
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Для получения дополнительных сведений ознакомьтесь со статьей [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Проверка

Для проверки подлинности можно использовать любой клиент Skype для бизнеса, чтобы войти в созданную учетную запись.

