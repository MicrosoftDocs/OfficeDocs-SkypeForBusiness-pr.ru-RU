---
title: Обновление Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Узнайте, как обновить развертывание Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359295"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Обновление Cloud Connector

> [!Important]
> Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online. После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)
 
Узнайте, как обновить развертывание Cloud Connector Edition.
  
If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically - according to your automatic update time window configuration. Вы также можете выполнить обновление вручную. 
  
Cloud Connector Edition версий 1.4.1 и более поздних версий выполняет автоматические обновления по умолчанию. Если вы хотите обновить до последней версии (2.1) вручную, см. раздел "Обновление одного сайта до новой версии" далее в этом разделе. [](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)
  
Автоматическое обновление требует, чтобы служба Cloud Connector была запущена. Ниже описан процесс автоматического обновления.
  
- Процесс автоматического обновления будет запускаться в соответствии с расписанием, настроенным для автоматического обновления.
    
- Задачи обновления операционной системы
    
  - Проверьте и скачайте обновления операционной системы на все ВМ Cloud Connector. 
    
  - Установите и обновите все ВМ Cloud Connector по одному и перезапустите.
    
  - После перезапуска ВМ Cloud Connector проверьте, требуется ли еще один перезапуск.
    
  - После успешного исправления ВМ Cloud Connector повторите процесс для хост-компьютера Cloud Connector.
    
  - После успешной загрузки хост-компьютера Cloud Connector все оставшиеся задачи обновления операционной системы будут выполнены.
    
- Задачи обновления Cloud Connector
    
  - Скачайте и проверьте файл версии с сайта загрузки.
    
  - Скачайте MSI-файл новой версии. 
    
  - Удалить старый MSI-файл; установите новый MSI-файл.
    
  - Скачайте новую версию битов Skype для бизнеса.
    
  - Зарегистрируйте устройство, вызывая Register-CcAppliance.
    
  - Установите новую версию Cloud Connector.
    
  - Осушить старое устройство и переключить сетевое подключение на новое устройство.
    
> [!NOTE]
>  При обновлении Cloud Connector до новой сборки, возможно, они не обновляются. Это может произойти, например, если окно PowerShell остается открытым во время автоматического обновления. Чтобы загрузить обновленные cmdlets, можно выполнить один из следующих действий: > Закрыть PowerShell на устройстве Cloud Connector, а затем повторно открыть PowerShell.> Или можно запустить Import-Module CloudConnector -Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Обновление отдельного сайта до новой версии
<a name="BKMK_Upgrade"> </a>

Если на сайте, который вы хотите обновить, есть только одно устройство, сделайте следующее:
  
1. Удалить существующую версию Cloud Connector в программах и программах панели **управления. \> \>**
    
2. Установите новую версию CloudConnector.msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) из .
    
3. Подтвердите наличие CloudConnector.ini версии, которую вы устанавливаете, и что вы обновили все необходимые значения для среды. Ini-файл из предыдущего выпуска использовать нельзя. Если вы обновляете Cloud Connector, обратитесь к разделу "Подготовка устройства [Cloud Connector"](prepare-your-cloud-connector-appliance.md) и убедитесь, что для siteName и EnableReferSupport установлено правильное значение в файле CloudConnector.ini.
    
4. Запустите консоль PowerShell от учетной записи администратора и запустите следующий cmdlet для регистрации текущего устройства:
    
   ```powershell
   Register-CcAppliance
   ```

5. Чтобы скачать последнюю версию, запустите следующий cmdlet:
    
   ```powershell
   Start-CcDownload
   ```

6. Чтобы запустить установку, запустите следующий cmdlet: 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. Чтобы активировать новое развертывание и отключить предыдущую версию, запустите следующий cmdlet:
    
   ```powershell
   Switch-CcVersion
   ```

Если на сайте несколько устройств, выполните следующие действия, чтобы обновить каждое устройство по одному.
  
Если требуется обновить учетные данные администратора домена, виртуальной машины, администратора безопасного режима и администратора клиента, можно выполнить его с параметром  _UpdateAllCredentials,_ чтобы сбросить все учетные данные:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Затем, когда вы начнете обновление до новой версии, вам будет назначено повышение, чтобы ввести новые учетные данные. 
  
Чтобы сбросить только учетные данные администратора клиента, запустите следующий cmdlet:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Обновление нескольких сайтов до новой версии
<a name="BKMK_Upgrade"> </a>

Выполните действия по обновлению отдельного сайта, обновляя по одному сайту за раз для каждого сайта в развертывании. Убедитесь, что [развертывание Cloud Connector](validate-your-cloud-connector-deployment.md) развернуто и проверено после обновления каждого сайта.
  

