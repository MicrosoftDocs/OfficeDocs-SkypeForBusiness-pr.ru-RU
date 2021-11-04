---
title: Развертывание клиентов для Skype для бизнеса Server
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: Сводка. Обзор методов установки корпоративных клиентов для Skype для бизнеса.
ms.openlocfilehash: 60da950c4ef330f704d45944a900e579478c558c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778929"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Развертывание клиентов для Skype для бизнеса Server
 
**Сводка:** Обзор методов установки корпоративных клиентов для Skype для бизнеса.
  
Развертывание Skype для бизнеса пользователей зависит от того, приобрели ли вы Skype для бизнеса в рамках плана Microsoft 365 или Office 365 или приобрели лицензированную версию Skype для бизнеса. 
  
- **Microsoft 365 или Office 365** Если у вас есть Microsoft 365 или Office 365, который включает Skype для бизнеса, используемая технология установки называется Click-to-Run. Вы можете позволить пользователям устанавливать Skype для бизнеса для себя с Центр администрирования Microsoft 365. Или вы можете развернуть Skype для бизнеса пользователям, скачав программное обеспечение в локализованную сеть, а затем используя существующие средства развертывания программного обеспечения, например Microsoft Endpoint Configuration Manager. Сведения об установке Skype для бизнеса, которые Microsoft 365 и Office 365, см. в Skype для бизнеса клиенте Microsoft 365 [или Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)
    
- **Том лицензирован** Если у вас есть лицензированная версия клиента Skype для бизнеса 2015 или 2016 года, используемая технология установки Windows установки (MSI). Пакет Windows установки на основе установки состоит из нескольких MSI-файлов. Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт. При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры. Клиент Skype для бизнеса 2019 года использует установщики click-to-Run.
    
В этом разделе описаны темы использования и настройки Windows установки для развертывания Skype для бизнеса клиента для пользователей с помощью обычных процедур.
  
> [!NOTE]
> Надстройка Skype собрания для Microsoft Office, которая поддерживает управление собраниями из Outlook обмена сообщениями и совместной работы, устанавливается автоматически с Skype для бизнеса клиентами. 
  
> [!NOTE]
> Программы Microsoft 365 и Office 365 не отмыкают предыдущие версии Lync. Клиент Skype для бизнеса устанавливается бок о бок с другими клиентами Lync. 
  
## <a name="installing-windows-clients"></a>Установка Windows клиентов

- [Настройка установки Windows клиента в Skype для бизнеса Server](customize-windows-client-installation.md)
    
- [Настройка клиентского опыта с помощью Skype для бизнеса](configure-the-client-experience.md)
    
- [Настройка списка контактов Smart в Skype для бизнеса Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Установка клиентов устройств

- [Установка и тестирование Skype для бизнеса на Windows Phone](windows-phone.md)
    
- [Установка и тестирование Skype для бизнеса для iOS](ios.md)
    
    
- [Развертывание плагина VDI Lync с помощью Skype для бизнеса Server](deploy-the-lync-vdi-plug-in.md)
    
- [Развертывание веб-загружаемых клиентов в Skype для бизнеса Server](deploy-web-downloadable-clients.md)
    
- [Настройка клиентского опыта Mac в Skype для бизнеса](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>См. также

[Развертывание Skype для бизнеса клиента в Microsoft 365 или Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
