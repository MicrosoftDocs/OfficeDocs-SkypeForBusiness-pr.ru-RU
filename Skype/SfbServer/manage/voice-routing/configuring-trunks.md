---
title: Настройка магистрали в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В рамках Корпоративная голосовая связь развертывания можно настроить магистраль между сервером-посредником и одним или несколькою однорангами, чтобы обеспечить подключение к общедоступным переключаемой телефонной сети (PSTN) для Корпоративная голосовая связь клиентов и устройств в вашей организации.
ms.openlocfilehash: 82491d566e36ce819456c3d2a8983f97dd6c4f17d4d7cece71a066342d48efea
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333461"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Настройка магистрали в Skype для бизнеса Server

В рамках Корпоративная голосовая связь развертывания можно настроить магистраль между сервером-посредником и одним или более из следующих одноранговых серверов, чтобы обеспечить подключение к общедоступным телефонным сетям (PSTN) для Корпоративная голосовая связь клиентов и устройств в вашей организации:

- Подключение магистрали SIP к поставщику услуг Интернет-телефонии
- Шлюз ТСОП
- УАТС

Подробные сведения см. [в материале Plan for PSTN connectivity in Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)

> [!IMPORTANT]
> Прежде чем приступать к настройке магистрали, убедитесь что создана топология и что сервер-посредник и его одноранговый узел настроены и связаны друг с другом. Подробные сведения см. [в материале Определение шлюза в Topology Builder в Skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)

> [!NOTE]
> В рамках конфигурации магистрали вы можете включить функцию обхода Skype для бизнеса Server мультимедиа, которая позволяет средствам массовой информации обходить сервер-посредник. Магистрали можно настроить как с включенной, так и с выключенной функцией медиа-посредника, но мы настоятельно рекомендуем включить эту функцию. Подробные сведения см. [в материале Plan for media bypass in Skype для бизнеса.](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
