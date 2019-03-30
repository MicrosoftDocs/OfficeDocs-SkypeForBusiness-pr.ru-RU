---
title: Развертывание клиентов для Скайп для Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Сводка: Обзор методов установки enterprise client для Скайп для бизнеса.'
ms.openlocfilehash: 49eff64918deefe2ec169993557dd0f9dfbf6955
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012541"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Развертывание клиентов для Скайп для Business Server
 
**Сводка:** Обзор корпоративных клиентов методы Скайп для бизнеса.
  
Как развернуть Скайп для бизнеса для пользователей зависит от того, является ли вы приобрели Скайп для бизнеса в рамках плана Office 365 или приобрести лицензированную версию тома Скайп для бизнеса. 
  
- **Office 365** Если у вас есть план Office 365, которая включает в себя Скайп для бизнеса, технология установки, которая используется называется Click-to-Run. В Office 365 можно позволить пользователям установить Скайп для бизнеса на свои компьютеры с портала Office 365. Или Скайп для бизнеса можно развернуть для пользователей, загрузив программное обеспечение в локальную сеть и затем с помощью существующие средства развертывания программного обеспечения, например, с помощью Microsoft System Center Configuration Manager. Сведения об установке о Скайп для бизнеса с Office 365 см [Скайп для клиента бизнеса в Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Том с корпоративным лицензированием** При наличии лицензированную версию Скайп для бизнеса 2015 или клиента 2016 многопользовательской установки технология, которая используется — установщика Windows (MSI). Пакет установки на основе установщика Windows состоит из нескольких файлов MSI. Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт. При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры. Скайп для клиента Business 2019 использует Click-to-Run программы установки.
    
В этом разделе описываются способы использования и настройки установщика Windows для развертывания Скайп для клиента Business для пользователей с помощью обычного процедур.
  
> [!NOTE]
> Надстройка собраний Скайп для Microsoft Office, которая поддерживает Управление собраниями в клиенте системы обмена сообщениями и совместной работы Outlook, автоматическая установка вместе с Скайп пользователей. 
  
> [!NOTE]
> Программа установки Office 365 не приводит к удалению предыдущих версий Lync. Скайп для клиента Business устанавливает рядом с другими клиентами Lync. 
  
## <a name="installing-windows-clients"></a>Установка клиентов Windows

- [Настройка установки клиента Windows в Скайп для Business Server](customize-windows-client-installation.md)
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [Настройка интеллектуального списка контактов в Skype для бизнеса Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Установка устройства клиентов

- [Install and test Skype for Business for Windows Phone](windows-phone.md)
    
- [Install and test Skype for Business for iOS](ios.md)
    
- [Развертывание системы комнат Skype в Skype для бизнеса Server](deploy-skype-room-system.md)
    
- [Развертывание групп Майкрософт комнат](room-systems-v2.md)
    
- [Развертывание подключаемого модуля VDI Lync с Скайп for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Развертывание веб-загрузки клиентов в Скайп для Business Server](deploy-web-downloadable-clients.md)
    
- [Настройка клиента на Mac в Skype для бизнеса](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>См. также

[Развертывание Скайп для клиента бизнеса в Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)