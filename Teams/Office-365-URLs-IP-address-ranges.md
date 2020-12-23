---
title: URL-адреса и диапазоны IP-адресов Microsoft 365 и Office 365
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Узнайте, как правильно настроить URL-адреса и диапазоны IP-адресов Microsoft 365 или Office 365, а также обойти прокси-сервер, если это возможно, для подключений к службе Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ad3ffdfd47b67ce21fb7f47a911afa67159f3e7
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650822"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL-адреса и диапазоны IP-адресов Microsoft 365 и Office 365
=======================================================

Перейдите на URL-адреса и диапазоны IP-адресов [Microsoft 365 и Office 365,](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) чтобы получить подробный и новый список URL-адресов, IP-адресов, портов и протоколов, которые необходимо правильно настроить для Teams. Корпорация Майкрософт непрерывно совершенствует службы Microsoft 365 и Office 365 и добавляет новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться. Мы рекомендуем вам [подписаться через RSS](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), чтобы получать уведомления при изменении или обновлении этой информации.

Интерфейс звонков и собраний в Teams основан на облачной инфраструктуре следующего поколения, которая также применяется в Skype и Skype для бизнеса. К таким технологическим нововведениям относятся облачные службы для обработки мультимедиа и сигнализации на основе Azure, видеокодек H.264, аудиокодек SILK и Opus, устойчивость сети, телеметрия и диагностика качества связи. Таким образом, в число требований входят URL- и IP-адреса, которые могут быть сопоставлены как со Skype, так и со Skype для бизнеса.

Для всех рабочих нагрузок Microsoft 365 и Office 365 рекомендуемый способ подключения к службам Teams по возможности обходит перенаский прокси-сервер. Если прокси-сервер находится между клиентом и центрами обработки данных Office 365, мультимедийный трафик может принудительно передаваться по протоколу TCP вместо UDP, что негативно повлияет на качество связи. Скачайте образцы PAC-файлов прокси-сервера, которые можно использовать для настройки обхода трафика для управления конечными точками [Microsoft 365 и Office 365.](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)

Если для сетевых политик и политик безопасности требуется трафик Microsoft 365 или Office 365 для прокси-сервера, перед развертыванием Teams в производственной сфере убедитесь, что эти требования уже выполнены. Дополнительные сведения можно получить на [прокси-серверах для Teams или Skype для бизнеса Online.](proxy-servers-for-skype-for-business-online.md)
