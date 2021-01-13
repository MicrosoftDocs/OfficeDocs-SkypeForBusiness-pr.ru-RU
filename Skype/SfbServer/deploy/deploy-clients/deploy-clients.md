---
title: Развертывание клиентов для Skype для бизнеса Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: Сводка. Обзор методов установки корпоративных клиентов для Skype для бизнеса.
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805699"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Развертывание клиентов для Skype для бизнеса Server
 
**Сводка:** Обзор методов установки корпоративных клиентов для Skype для бизнеса.
  
Развертывание Skype для бизнеса для пользователей зависит от того, приобрели ли вы Skype для бизнеса в рамках плана Microsoft 365 или Office 365 или приобрели версию Skype для бизнеса с много лицензиями. 
  
- **Microsoft 365 или Office 365** Если у вас есть план Microsoft 365 или Office 365, который включает Skype для бизнеса, используемая технология установки называется технологией "нажми и запускай". Вы можете позволить пользователям самостоятельно устанавливать Skype для бизнеса из Центра администрирования Microsoft 365. Кроме того, вы можете развернуть Skype для бизнеса для пользователей, скачав программное обеспечение в локализованную сеть, а затем используя существующие средства развертывания программного обеспечения, например Microsoft Endpoint Configuration Manager. Сведения об установке Skype для бизнеса, которая поставляется вместе с Microsoft 365 и Office 365, см. в сведениях о развертывании клиента Skype для бизнеса в [Microsoft 365 или Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)
    
- **Volume licensed** Если у вас есть клиент Skype для бизнеса 2015 или 2016 с много лицензией, используемая технология установки — установщик Windows (MSI). Пакет установки на основе установщика Windows состоит из нескольких MSI-файлов. Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт. При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры. Клиент Skype для бизнеса 2019 использует установщики "нажми и выйми".
    
В темах этого раздела описывается использование и настройка установщика Windows для развертывания клиента Skype для бизнеса для пользователей с помощью обычных процедур.
  
> [!NOTE]
> Надстройка для собраний Skype для Microsoft Office, которая поддерживает управление собраниями в клиенте outlook для обмена сообщениями и совместной работы, устанавливается автоматически с клиентами Skype для бизнеса. 
  
> [!NOTE]
> Программы установки Microsoft 365 и Office 365 не будут удалить предыдущие версии Lync. Клиент Skype для бизнеса устанавливается вместе с другими клиентами Lync. 
  
## <a name="installing-windows-clients"></a>Установка клиентов Windows

- [Настройка установки клиента Windows в Skype для бизнеса Server](customize-windows-client-installation.md)
    
- [Настройка работы с клиентом в Skype для бизнеса](configure-the-client-experience.md)
    
- [Настройка интеллектуального списка контактов в Skype для бизнеса Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Установка клиентов устройств

- [Установка и тестирование Skype для бизнеса для Windows Phone](windows-phone.md)
    
- [Установка и тестирование Skype для бизнеса для iOS](ios.md)
    
    
- [Развертывание подключаемого модуль Lync VDI со Skype для бизнеса Server](deploy-the-lync-vdi-plug-in.md)
    
- [Развертывание загружаемых веб-клиентов в Skype для бизнеса Server](deploy-web-downloadable-clients.md)
    
- [Настройка клиентского опыта Mac в Skype для бизнеса](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>См. также

[Развертывание клиента Skype для бизнеса в Microsoft 365 или Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
