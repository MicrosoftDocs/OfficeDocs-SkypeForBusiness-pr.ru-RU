---
title: Настройка магистральных магистральных звонков в Skype для бизнеса Server
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
description: В рамках Корпоративная голосовая связь вы можете настроить магистраль между сервером-посредником и одним или более одноранговых узлами, чтобы обеспечить подключение к телефонной сети общего слева (PSTN) для Корпоративная голосовая связь клиентов и устройств в организации.
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800119"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Настройка магистральных магистральных звонков в Skype для бизнеса Server

В рамках развертывания Корпоративная голосовая связь можно настроить магистраль между сервером-посредником и одним или более из следующих одноранговых серверов, чтобы обеспечить подключение к STN для клиентов Корпоративная голосовая связь и устройств в организации:

- Подключение магистрали SIP к поставщику услуг Интернет-телефонии
- Шлюз ТСОП
- УАТС

For details, see [Plan for PSTN connectivity in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)

> [!IMPORTANT]
> Прежде чем приступать к настройке магистрали, убедитесь что создана топология и что сервер-посредник и его одноранговый узел настроены и связаны друг с другом. For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> В рамках настройки магистрали можно включить функцию обхода сервера-посредника Skype для бизнеса Server, которая позволяет мультимедиа обходить сервер-посредник. Магистрали можно настроить как с включенной, так и с выключенной функцией медиа-посредника, но мы настоятельно рекомендуем включить эту функцию. For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
