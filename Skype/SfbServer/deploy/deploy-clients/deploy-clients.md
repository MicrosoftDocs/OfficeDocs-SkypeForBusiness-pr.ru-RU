---
title: Развертывание клиентов для Skype для бизнеса Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Сводка: обзор способов установки корпоративных клиентов для Skype для бизнеса.'
ms.openlocfilehash: 8d6e59582c3c420d5752a84f793e6c3025b3c500
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220649"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Развертывание клиентов для Skype для бизнеса Server
 
**Сводка:** Обзор способов установки корпоративных клиентов для Skype для бизнеса.
  
Способ развертывания Skype для бизнеса для пользователей зависит от того, приобрели ли вы Skype для бизнеса в рамках плана Microsoft 365 или Office 365 либо вы приобрели Skype для бизнеса с корпоративной лицензией. 
  
- **Microsoft 365 или Office 365** Если у вас есть план Microsoft 365 или Office 365, включающий Skype для бизнеса, то используемая технология установки называется "нажми и работай". Пользователи могут самостоятельно установить Skype для бизнеса в центре администрирования Microsoft 365. Вы также можете развернуть Skype для бизнеса для пользователей, загрузив программное обеспечение в локальную сеть, а затем используя существующие средства развертывания программного обеспечения, например с помощью диспетчера конфигураций конечных точек Майкрософт. Сведения об установке Skype для бизнеса, поставляемые с Microsoft 365 и Office 365, приведены [в статье Развертывание клиента Skype для бизнеса в microsoft 365 или office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Корпоративная лицензия** Если вы используете версию клиента Skype для бизнеса 2015 или 2016 с корпоративной лицензией, используемая технология установки — установщик Windows (MSI). Пакет установки на основе установщика Windows состоит из нескольких MSI файлов. Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт. При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры. В клиенте Skype для бизнеса 2019 используются установщики "нажми и работай".
    
В подразделах этого раздела описывается, как использовать и настраивать установщик Windows для развертывания клиента Skype для бизнеса для пользователей с помощью обычных процедур.
  
> [!NOTE]
> Надстройка "собрание Skype" для Microsoft Office, которая поддерживает управление собраниями в клиенте обмена сообщениями и совместной работы Outlook, устанавливается автоматически с клиентами Skype для бизнеса. 
  
> [!NOTE]
> Программы установки Microsoft 365 и Office 365 не удаляют предыдущие версии Lync. Клиент Skype для бизнеса устанавливается параллельно с другими клиентами Lync. 
  
## <a name="installing-windows-clients"></a>Установка клиентов Windows

- [Настройка установки клиента Windows в Skype для бизнеса Server](customize-windows-client-installation.md)
    
- [Настройка взаимодействия с клиентом с помощью Skype для бизнеса](configure-the-client-experience.md)
    
- [Настройка списка смарт-контактов в Skype для бизнеса Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Установка клиентов устройств

- [Установка и тестирование Skype для бизнеса для Windows Phone](windows-phone.md)
    
- [Установка и тестирование Skype для бизнеса для iOS](ios.md)
    
    
- [Развертывание подключаемого модуля VDI для Lync с помощью Skype для бизнеса Server](deploy-the-lync-vdi-plug-in.md)
    
- [Развертывание веб-клиентов, загружаемых через Интернет, в Skype для бизнеса Server](deploy-web-downloadable-clients.md)
    
- [Настройка взаимодействия с клиентом Mac в Skype для бизнеса](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>См. также

[Развертывание клиента Skype для бизнеса в Microsoft 365 или Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
