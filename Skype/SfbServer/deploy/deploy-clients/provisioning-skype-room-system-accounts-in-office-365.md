---
title: Предоставление учетных записей системы комнат Skype в Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: В этом разделе описывается выделение учетных записей системы комнат Skype в Office 365.
ms.openlocfilehash: 87643d04879888d59739c997e37108c6c7403101
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301542"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Предоставление учетных записей системы комнат Skype в Office 365
 
В этом разделе описывается выделение учетных записей системы комнат Skype в Office 365.
  
В следующем разделе приводится описание подготовки учетной записи системы Skype для клиента Office 365.
  
## <a name="office-365-prerequisites"></a>Предварительные требования для Office 365

Сетевой клиент должен удовлетворять следующим требованиям:
  
- План Office 365 должен включать Skype для бизнеса Online (план 2) или Office 365 E1, E3 или 3. <br/>Подробнее о тарифах Skype для бизнеса Online можно найти в [описании службы Skype для бизнеса Online](https://technet.microsoft.com/library/jj822172.aspx).
    
- В клиенте должна быть включена возможность проведения Конференции в Skype для бизнеса.
    
- У пользователя должно быть включено приложение Exchange Online. 
    
- Удаленный администратор пользователя должен иметь следующие права доступа PowerShell:
    
  - Удаленный доступ PowerShell к Exchange
    
  - Удаленный доступ к PowerShell в Skype для бизнеса Online
    
  - Модуль Windows Azure Active Directory для Windows PowerShell для доступа к каталогу Office 365
    
Для учетной записи комнаты Skype необходимы следующие лицензии::
  
- Для включения собраний Skype требуется лицензия Skype для бизнеса Online (план 2) или Office 365 E1 или E3.
    
- Чтобы предоставить доступ к комнате с помощью корпоративной голосовой связи, чтобы можно было использовать телефонный номер, требуется Skype для бизнеса Online (план 2) с лицензией на телефонную систему или Office 365 3 (1).
    
- Если вам понадобятся возможности телефонного подключения к собранию, вам потребуется голосовой Конференц-связь и лицензия на телефонную систему.  Если вам нужны возможности исходящих звонков с собрания, вам понадобится план внутренних или внутренних и международных звонков. 
    
- Лицензия Exchange Online не требуется для учетной записи комнаты Skype, так как эта учетная запись должна настраиваться как учетная запись почтового ящика ресурса.
    
## <a name="provisioning-overview"></a>Обзор предоставления

На приведенной ниже схеме представлен обзор процесса подготовки учетной записи системы для помещения в Skype в Office 365.
  
![Этапы подготовки системы для комнаты Skype для O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Создание новой комнаты переговоров

Возможно, у вас уже есть почтовый ящик из комнаты ресурсов в Exchange, в котором есть функция планирования, или вы можете создать почтовый ящик ресурсов в первый раз, чтобы упростить развертывание системы комнаты Skype. В обоих случаях необходимо создать учетную запись комнаты, которая будет использоваться в клиенте. Разделы подготовки Exchange Online и Skype для бизнеса содержат рекомендации для обоих типов учетных записей. Например, предположим, что у вас есть две комнаты, и вы хотите развернуть систему комнат Skype для обоих из них:
  
- Текущая учетная запись почтового ящика ресурсов: confrm1@contoso.onmicrosoft.com
    
- Новая учетная запись почтового ящика ресурсов: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Предоставление Exchange Online

Сначала подключитесь к Exchange Online PowerShell, следуя инструкциям в этой статье, [подключитесь к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Чтобы настроить существующую учетную запись почтового ящика для помещения в комнату для Skype, выполните следующие команды в Exchange Online PowerShell.
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Чтобы создать новую учетную запись почтового ящика Exchange для системы комнат Skype, выполните в Exchange Online PowerShell следующие команды:
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Предыдущие команды настроили или создали новую учетную запись почтового ящика Exchange для помещения в Skype, включив учетную запись.
  
Создав почтовый ящик, вы можете настроить почтовый ящик с помощью командлета Set-Календарпроцессинг в Exchange Online PowerShell. Дополнительные сведения см. в разделе "Развертывание одного локального леса", шаги 3–6.

## <a name="assigning-a-skype-for-business-online-license"></a>Назначение лицензии Skype для бизнеса Online

Теперь вы можете назначить лицензию Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3) с помощью административного портала Office 365, как описано в разделе [назначение и удаление лицензий для office 365 для бизнеса](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) или в [надстройке Skype для бизнеса Лицензирование](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
После назначения лицензии Skype для бизнеса Online вы сможете войти в систему и подтвердить, что она активна с помощью любого клиента Skype для бизнеса.
  
## <a name="skype-for-business-online-provisioning"></a>Предоставление Skype для бизнеса Online

После создания и включения учетной записи почтового ящика для ресурсов, как показано выше, и активации учетной записи в Skype для бизнеса Online учетная запись будет синхронизирована с лесом Exchange Online и в лесу Skype для бизнеса Online с помощью Лес Windows Azure Active Directory. Для подготовки учетной записи системы комнаты Skype в пуле Skype для бизнеса Online необходимо выполнить указанные ниже действия. Эти действия одинаковы для существующей учетной записи почтового ящика ресурса или вновь созданной учетной записи (confrm1 или confrm2), поскольку обе эти учетные записи будут синхронизироваться с Skype для бизнеса Online так же, как и в Exchange Online.
  
1. Создайте удаленный сеанс PowerShell. Обратите внимание, что для этого вам потребуется загрузить модуль соединителя Skype для бизнеса Online и помощник по входу в Microsoft Online Services и проверить, настроен ли ваш компьютер. Дополнительные сведения можно найти в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Чтобы включить учетную запись системы комнаты Skype для Skype для бизнеса, выполните следующую команду:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Вы можете получить адрес Регистрарпул, на котором пользователи Skype для бизнеса находятся в одной из существующих учетных записей, выполнив следующую команду, чтобы возвратить это свойство:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>Срок действия пароля

В Office 365 политика истечения срока действия паролей по умолчанию для всех учетных записей пользователей составляет 90 дня, если вы не настроили другую политику срока действия паролей. Для системных учетных записей комнаты Skype вы можете выбрать пароль, который не может быть указан, выполнив указанные ниже действия.
  
1. Создайте сеанс Windows Azure Active Directory, указав учетные данные глобального администратора клиента.
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Настройка пароля не действует для учетной записи комнаты системы комнат Skype, созданной ранее с помощью следующей команды:
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Дополнительные сведения можно найти в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Действитель

Для проверки подлинности вы можете использовать любой клиент Skype для бизнеса для входа в созданную учетную запись.

