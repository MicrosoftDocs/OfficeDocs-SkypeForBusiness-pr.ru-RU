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
description: 'Сводка: Общие сведения о методах установки корпоративных клиентов для Skype для бизнеса.'
ms.openlocfilehash: 0e7859fe207ed80aa7dceef794aa57d15cc0c79b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768732"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Развертывание клиентов для Skype для бизнеса Server
 
**Сводка:** Общие сведения о методах установки корпоративных клиентов для Skype для бизнеса.
  
Способ развертывания Skype для бизнеса для пользователей зависит от того, приобрели ли вы Skype для бизнеса как часть плана Office 365 или вы приобрели корпоративную версию Skype для бизнеса с корпоративной лицензией. 
  
- **Office 365** Если вы используете план Office 365, включающий Skype для бизнеса, используется технология установки, которая называется "нажми и работай". С помощью Office 365 вы можете установить Skype для бизнеса для пользователей на портале Office 365. Кроме того, вы можете развернуть Skype для бизнеса для пользователей, загрузив программное обеспечение в локальную сеть и используя существующие средства развертывания программного обеспечения (например, с помощью диспетчера конфигураций конечных точек Microsoft). Сведения об установке Skype для бизнеса, которые поставляются вместе с Office 365, можно найти [в разделе Развертывание клиента Skype для бизнеса в office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Корпоративное лицензирование** Если у вас есть лицензированная Корпоративная версия клиента Skype для бизнеса 2015 или 2016, используется технология установки, которая является установщиком Windows (MSI). Пакет установки на основе установщика Windows состоит из нескольких MSI-файлов. Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт. При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры. В клиенте Skype для бизнеса 2019 используются установщики "нажми и работай".
    
В этом разделе описано использование и Настройка установщика Windows для развертывания клиента Skype для бизнеса для пользователей с помощью обычных процедур.
  
> [!NOTE]
> Надстройка "собрание Skype" для Microsoft Office, поддерживающая управление собраниями в клиенте обмена сообщениями и совместной работы в Outlook, устанавливается автоматически с помощью клиентов Skype для бизнеса. 
  
> [!NOTE]
> Программа установки Office 365 не удаляет предыдущие версии Lync. Клиент Skype для бизнеса устанавливается рядом с другими клиентами Lync. 
  
## <a name="installing-windows-clients"></a>Установка клиентов Windows

- [Настройка установки клиента Windows в Skype для бизнеса Server](customize-windows-client-installation.md)
    
- [Настройка взаимодействия с клиентом в Skype для бизнеса](configure-the-client-experience.md)
    
- [Настройка интеллектуального списка контактов в Skype для бизнеса Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Установка клиентов устройства

- [Install and test Skype for Business for Windows Phone](windows-phone.md)
    
- [Install and test Skype for Business for iOS](ios.md)
    
    
- [Развертывание плагина Lync VDI с помощью Skype для бизнеса Server](deploy-the-lync-vdi-plug-in.md)
    
- [Развертывание веб-клиентов, доступных для загрузки, в Skype для бизнеса Server](deploy-web-downloadable-clients.md)
    
- [Настройка клиента на Mac в Skype для бизнеса](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>См. также

[Развертывание клиента Skype для бизнеса в Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
