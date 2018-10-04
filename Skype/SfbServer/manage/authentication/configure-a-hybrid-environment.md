---
title: Настройка проверки подлинности сервер сервер для Скайп для гибридной среды Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Сводка: Настройка проверки подлинности сервер сервер для Скайп для гибридной среды Business Server.'
ms.openlocfilehash: 02412c152e017da95c82ff6f8ad6f08db1a105ef
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375952"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Настройка проверки подлинности сервер сервер для Скайп для гибридной среды Business Server.

**Сводка:** Настройка проверки подлинности сервер сервер для Скайп для гибридной среды Business Server.

В гибридной конфигурации некоторые пользователи размещаются в локальной установки Скайп для Business Server в то время как другие пользователи размещаются в версии Office 365 Скайп для Business Server. Чтобы настроить проверку подлинности сервер сервер в гибридной среде, необходимо настроить своей локальной установки Скайп для Business Server для доверия серверу авторизации Office 365. Первым шагом этот процесс может быть выполнено, выполнив следующие Скайп для скрипта консоли Business Server:

```
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Помните о том, что имя области для клиента обычно отличается от имени организации; на деле имя области почти всегда совпадает с идентификатором клиента. Поэтому первая строка скрипта используется для получения значения свойства TenantId для заданного клиента (в данном случае это fabrikam.com) и последующего назначения этого имени переменной $TenantId:

```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

После выполнения скрипта необходимо настроить отношения доверия между Скайп для Business Server и сервера авторизации и второй отношения доверия между Exchange 2013 и сервера авторизации. Это возможно только с помощью командлетов Microsoft Online Services.

> [!NOTE]
> Если командлеты Microsoft Online Services не установлены, потребуется выполнить две операции перед тем, как продолжить. Во-первых, скачайте и установите 64-разрядную версию помощника по входу в Microsoft Online Services. После завершения установки, загрузите и установите 64-разрядная версия Microsoft Online Services модуль для Windows PowerShell. Подробные сведения по установке и использованию модуль Microsoft Online Services можно найти на веб-сайте Office 365. Эти инструкции также можно узнать, как настроить единый вход, федерации и синхронизации между Office 365 и Active Directory. 

Если вы не выполнили установку этих командлетов, то произойдет сбой вашего сценария, так как командлет Get-CsTenant будет недоступен.

После настройки Office 365, и после создания Office 365 субъектов-служб для Скайп для Business Server и Exchange 2013, затем нужно зарегистрировать свои учетные данные в этих субъектов-служб. Для этого необходимо сначала получить X.509 Base64 в виде файла CER. Этот сертификат затем будет применяться к участников службы Office 365.

После получения сертификата X.509, начать модуль Microsoft Online Services (нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Microsoft Online Services**и нажмите кнопку **Microsoft Online Services модуль для Windows PowerShell**). После открытия модуля службы, введите следующие действия, чтобы импортировать модуль Microsoft Online Windows PowerShell, содержащий командлетов, которые можно использовать для управления субъектов-служб:

```
Import-Module MSOnlineExtended
```

По завершении импорта модуля введите следующую команду и нажмите клавишу ВВОД для подключения к Office 365:

```
Connect-MsolService
```

При нажатии клавиши Enter отображается диалоговое окно учетных данных. В диалоговом окне введите имя пользователя Office 365 и пароль и нажмите кнопку ОК.

Как только вы подключены к Office 365, можно затем выполните следующую команду для получения информации о субъектах:

```
Get-MsolServicePrincipal
```

Команда возвращает для всех субъектов-служб сведения, похожие на следующие:

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

На следующем шаге выполняется импорт, кодирование и назначение сертификата X.509. Импорт и кодирования сертификат, используйте следующие команды Windows PowerShell, убедитесь указать полный путь к вашей. Файл CER при вызове метода импорта:

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

После того как сертификат был импортирован и кодировке, затем можно назначить сертификат для субъектов-служб Office 365. Для этого сначала командлет Get-MsolServicePrincipal для получения значение свойства AppPrincipalId для Скайп для Business Server и участников службы Microsoft Exchange; значение свойства AppPrincipalId будет использоваться для идентификации участников-служб, назначаемое сертификат. С помощью AppPrincipalId свойство руку значение для Скайп Business Server, выполните следующую команду назначение сертификата до версии Office 365 Скайп для Business Server.

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Необходимо повторно выполнить команду, это время с помощью значение свойства AppPrincipalId для Exchange 2013.

Если позднее вам потребуется удалить этот сертификат, сначала вам потребуется получить для него значение KeyId:

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Эта команда возвращает следующие данные:

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

После этого вы можете удалить сертификат с помощью следующей команды:

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

В дополнение к назначения сертификата, который необходимо настроить Exchange Online участников-служб и настройка локальной версии Скайп для Business Server внешние Web services URL-адреса в качестве участника-службы Office 365. Для этого можно выполнить две следующие команды: 

В следующем примере lync.contoso.com является внешним Web services URL-адрес Скайп для пула Business Server. Следует повторите эти действия, чтобы добавить всех внешних Web services URL-адреса в развертывании.

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```