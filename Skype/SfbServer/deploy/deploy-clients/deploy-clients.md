---
title: Развертывание клиентов для Skype для бизнеса Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Сводка: Обзор методов установки enterprise client для Скайп для бизнеса.'
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a>Развертывание клиентов для Skype для бизнеса Server 2015
 
**Сводка:** Обзор корпоративных клиентов методы Скайп для бизнеса.
  
Как развернуть Скайп для бизнеса для пользователей зависит от того, является ли вы приобрели Скайп для бизнеса в рамках плана Office 365 или приобрести лицензированную версию тома Скайп для бизнеса. 
  
- **Office 365** Если у вас есть план Office 365, которая включает в себя Скайп для бизнеса, технология установки, которая используется называется Click-to-Run. В Office 365 можно позволить пользователям установить Скайп для бизнеса на свои компьютеры с портала Office 365. Или Скайп для бизнеса можно развернуть для пользователей, загрузив программное обеспечение в локальную сеть и затем с помощью существующие средства развертывания программного обеспечения, например, с помощью Microsoft System Center Configuration Manager. Сведения об установке о Скайп для бизнеса с Office 365 см [Скайп для клиента бизнеса в Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Том с корпоративным лицензированием** Если у вас есть корпоративной лицензии ОС Скайп для бизнеса, технология установки, которая используется — установщика Windows (MSI). Пакет установки на основе установщика Windows состоит из нескольких файлов MSI. Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт. При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры.
    
В этом разделе описываются способы использования и настройки установщика Windows для развертывания Скайп для клиента Business для пользователей с помощью обычного процедур.
  
> [!NOTE]
> Online собрания надстройки для Скайп для бизнеса, который поддерживает собрания управления из приложения Outlook клиент обмена сообщениями и совместной работы, автоматическая установка вместе с Скайп для бизнеса. 
  
> [!NOTE]
> Программа установки Office 365 не приводит к удалению предыдущих версий Lync или Office Communicator. Скайп для клиента Business устанавливает рядом с другими клиентами Lync или Office Communicator. 
  
## <a name="installing-windows-clients"></a>Установка клиентов Windows

- [Настройка установки клиента Windows в Скайп для Business Server 2015](customize-windows-client-installation.md)
    
- [Настройка взаимодействия с пользователем с помощью Скайп для бизнеса](configure-the-client-experience.md)
    
- [Настройка списка смарт-контактов в Скайп для Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Установка устройства клиентов

- [Установка и тестирование Скайп для бизнеса для Windows Phone](windows-phone.md)
    
- [Установка и тестирование Скайп для бизнеса для операций ввода-вывода](ios.md)
    
- [Развертывание системы Скайп помещения в Скайп для Business Server](deploy-skype-room-system.md)
    
- [Развертывание Скайп комнаты систем версии 2](room-systems-v2.md)
    
- [Развертывание подключаемого модуля VDI Lync с Скайп для Business Server 2015](deploy-the-lync-vdi-plug-in.md)
    
- [Развертывание веб-загрузки клиентов в Скайп для Business Server 2015](deploy-web-downloadable-clients.md)
    
- [Настройка взаимодействия с пользователем Mac в Скайп для бизнеса](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>См. также

#### 

[Развертывание Скайп для клиента Business для вашей организации](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

