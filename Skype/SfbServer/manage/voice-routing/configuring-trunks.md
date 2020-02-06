---
title: Настройка каналов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В рамках развертывания Enterprise Voice вы можете настроить магистраль между сервером-посредником и одним или несколькими узлами для предоставления доступа к общественной коммутируемой телефонной сети (PSTN) для мобильных клиентов и устройств в Организации.
ms.openlocfilehash: 41e92f994606ea2153359546d408335d13a21f88
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817019"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Настройка каналов в Skype для бизнеса Server

В рамках развертывания Enterprise Voice вы можете настроить магистраль между сервером-посредником и одним или несколькими из указанных ниже одноранговых сетей для предоставления подключения по коммутируемой телефонной сети (PSTN) для корпоративных клиентов и мобильных устройств в Организации.

- Подключение магистрали SIP к поставщику услуг Интернет-телефонии
- Шлюз ТСОП
- УАТС

Подробнее смотрите в разделе [Планирование подключений PSTN в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Перед началом настройки магистрали убедитесь в том, что топология создана и что сервер исправлений и его одноранговые элементы настроены и связаны друг с другом. Подробности можно найти [в разделе определение шлюза в построителе топологии в Skype для бизнеса Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> В рамках настройки магистральной конфигурации вы можете включить функцию пропуска мультимедиа в Skype для бизнеса Server, которая позволяет мультимедиа обходить сервер-посредник. Магистральные магистрали можно настраивать с включенным параметром "обойти" или без него, но настоятельно рекомендуем включить его. Подробности можно найти [в разделе Планирование обхода мультимедиа в Skype для бизнеса](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
