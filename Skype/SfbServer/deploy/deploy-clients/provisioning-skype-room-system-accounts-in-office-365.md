---
title: Предоставление учетных записей системы комнат Skype в Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: В этом разделе описывается выделение учетных записей системы комнат Skype в Office 365.
ms.openlocfilehash: a1b24e25236f221d280631efd83c0e83b7ae44f2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219480"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Предоставление учетных записей системы комнат Skype в Office 365
 
В этом разделе описывается выделение учетных записей системы комнат Skype в Office 365.
  
В данном разделе рассматриваются Скайп комнаты системной учетной записью, подготовки для клиента Office 365.
  
## <a name="office-365-prerequisites"></a>Предварительные требования для Office 365

Сетевой клиент должен удовлетворять следующим требованиям:
  
- План Office 365 необходимо включить Скайп для бизнеса Online план 2, или Office 365 E1, E3 или E5. <br/>Дополнительные сведения о Скайп для бизнеса Online планы см [Скайп для описания службы Online бизнеса](https://technet.microsoft.com/library/jj822172.aspx).
    
- Клиент должен иметь возможности конференц-связи Скайп для бизнеса включен.
    
- У пользователя должно быть включено приложение Exchange Online. 
    
- Удаленный администратор пользователя должен иметь следующие права доступа PowerShell:
    
  - Удаленный доступ PowerShell к Exchange
    
  - Скайп для доступа к Business Online удаленной оболочки PowerShell
    
  - Windows Azure модуль Active Directory для Windows PowerShell для доступа к Office 365 доступ к каталогу
    
Для учетной записи комнаты Skype необходимы следующие лицензии::
  
- Скайп для бизнеса Online (план 2) или Office 365 E1 или E3 лицензия требуется для включения Скайп собрания.
    
- Для предоставления комнаты с возможностью корпоративной голосовой связи, поэтому комнаты можно включить с номером телефона, Скайп для бизнеса Online (план 2) с телефонной системой лицензии или Office 365 E5 является обязательным (1).
    
- Если вам требуется-связь с возможностями собрания, необходимо будет аудиоконференций и лицензии телефонной системой.  Если вам требуется подключение по телефонной линии возможности из собрания, необходимо будет внутри страны или внутреннее и международное вызов план. 
    
- Лицензия Exchange Online не требуется для учетной записи комнаты Skype, так как эта учетная запись должна настраиваться как учетная запись почтового ящика ресурса.
    
## <a name="provisioning-overview"></a>Обзор предоставления

Следующая схема Обзор подготовки поток в Office 365 Скайп комнаты системную учетную запись.
  
![Этапы подготовки системы для комнаты Skype для O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Создание новой комнаты переговоров

Вы уже может быть почтовый ящик ресурса помещения в Exchange, который предоставляет функции планирования или создаваемого почтового ящика ресурса в первый раз упростить развертывание системы Скайп помещений. В обоих случаях необходимо создать учетную запись комнаты, которая будет использоваться в клиенте. Exchange Online подготовки и Скайп для подготовки Business разделов, позволяют для обоих типов учетных записей. Например предположим, у вас есть следующие два комнат, и он хотел развертывания системы Скайп комнаты для их:
  
- Текущая учетная запись почтового ящика ресурсов: confrm1@contoso.onmicrosoft.com
    
- Новая учетная запись почтового ящика ресурсов: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Предоставление Exchange Online

Во-первых подключение к Exchange Online PowerShell, следуя инструкциям, приведенным в разделе [подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Чтобы настроить существующую учетную запись почтового ящика ресурса комнаты для системы Скайп помещения, выполните следующие команды в Exchange Online PowerShell:
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Чтобы создать новую учетную запись почтового ящика Exchange ресурсов для системы Скайп помещения, выполните следующие команды в Exchange Online PowerShell:
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Предыдущей команды настроить или создать новую учетную запись почтового ящика Exchange ресурсов для использования системы комнаты Скайп посредством включения учетной записи.
  
После создания почтового ящика, можно использовать командлет Set-CalendarProcessing в Exchange Online PowerShell для настройки почтового ящика. Дополнительные сведения см. в разделе "Развертывание одного локального леса", шаги 3–6.

## <a name="assigning-a-skype-for-business-online-license"></a>Назначение лицензии Skype для бизнеса Online

Теперь можно назначить Скайп для бизнеса Online (план 2) или Скайп для лицензии через Интернет бизнес (план 3) с помощью портала администрирования Office 365, как описано в [Назначение и удаление лицензий на Office 365 для бизнеса](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) или в [Скайп для бизнеса надстройки Лицензирование](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
После назначения лицензии для Скайп для бизнеса в Интернет, вы сможете для входа и убедиться, что учетная запись является активным, с помощью любого Скайп для клиента Business.
  
## <a name="skype-for-business-online-provisioning"></a>Предоставление Skype для бизнеса Online

После помещения ресурсов почтовый ящик учетной записи была создана и включена, как показано выше, и лицензированных учетной записи для Скайп для бизнеса в Интернет учетной записи будут синхронизироваться с Exchange Online леса для Скайп для бизнеса в Интернет леса с помощью Лес Windows Azure Active Directory. Подготовка Скайп комнаты системную учетную запись в Скайп для бизнеса в Интернет пула необходимы следующие действия. Эти шаги совпадают с существующей учетной записи ресурса почтового ящика или учетной записи только что созданный (confrm1 или confrm2), так как после их, необходимо включить в Exchange Online, оба этих учетных записей синхронизация с Скайп для бизнеса в Интернет так же, как:
  
1. Создайте удаленный сеанс PowerShell. Обратите внимание, что необходимо загрузить Скайп для бизнес-Online соединителя модуля и Microsoft Online Services помощника по входу и убедитесь в том, что на компьютере настроена. Дополнительные сведения можно [настроить компьютер для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Чтобы включить учетную запись системы комнаты Скайп для Скайп для бизнеса, выполните следующую команду:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Вы можете получить RegistrarPool, в котором расположена вашей Скайп для бизнес-пользователей из одного из существующих учетных записей, используя следующую команду, чтобы адрес возвращает этого свойства:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>Срок действия пароля

Если не настроить политику истечение срока действия пароля в Office 365, политика срока действия пароля по умолчанию для всех учетных записей пользователей — это 90 дней. Для Скайп помещений системных учетных записей, можно выбрать пароля неограничен виде с помощью следующих действий.
  
1. Создайте сеанс Windows Azure Active Directory, указав учетные данные глобального администратора клиента.
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Набор пароля неограничен параметр для учетной записи системы комнаты Скайп комнаты, созданную ранее с помощью следующей команды:
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Дополнительные сведения можно [настроить компьютер для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Проверка

Для проверки можно использовать любой Скайп для бизнеса клиента для входа в учетную запись, которую вы создали.

