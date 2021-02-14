---
title: Проверка федерации и удаленного доступа для внешних пользователей
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected. В тесты для внешних пользователей должны включаться все типы пользователей, поддерживаемые в организации, включая любой из типов (или все типы) из указанных ниже.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751671"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Проверка федерации и удаленного доступа для внешних пользователей

After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected. В тесты для внешних пользователей должны включаться все типы пользователей, поддерживаемые в организации, включая любой из типов (или все типы) из указанных ниже.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Проверка подключения внешних пользователей и внешнего доступа

- Пользователи по крайней мере из одного федератного домена, внутренний пользователь Skype для бизнеса Server 2019 и пользователь с устаревшей установкой. Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.
    
- Пользователи всех общедоступных поставщиков услуг im, поддерживаемые организацией (и для которых завершена подготовка), общаются с пользователем Skype для бизнеса Server 2019 и пользователем в устаревшей установке. 
    
- Проверьте, что анонимные пользователи могут присоединиться к конференциям.
    
- Пользователь, который находится в устаревшей установке с помощью удаленного доступа пользователей (записываясь в журнал i nto Lync Server или Skype для бизнеса из-за пределов интрасети, но без VPN), с пользователем в Skype для бизнеса Server 2019 и пользователем в устаревшей установке. Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.
    
- Пользователь, который находится в Skype для бизнеса Server 2019 с удаленным доступом (вход в Skype для бизнеса Server 2019 из-за пределов интрасети, но без VPN) с пользователем в Skype для бизнеса Server 2019 и пользователем с устаревшей установкой. Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.
    

