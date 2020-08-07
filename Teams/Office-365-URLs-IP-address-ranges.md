---
title: URL-адреса и диапазоны IP-адресов для Microsoft 365 и Office 365
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Сведения о том, как правильно настроить URL-адреса и диапазоны IP-адресов для Microsoft 365 или Office 365 и обходить прокси-сервер переадресации по возможности для подключений к службе Microsoft Teams.
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
ms.openlocfilehash: 94fd32cb4f68d636a6ff49ecf3b9c19689542142
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582126"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL-адреса и диапазоны IP-адресов для Microsoft 365 и Office 365
=======================================================

Перейдите на [URL-адреса и диапазоны IP-адресов для microsoft 365 и Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) , чтобы получить подробный и актуальный список URL-адресов, IP-адресов, портов и протоколов, которые должны быть правильно настроены для Teams. Корпорация Майкрософт непрерывно совершенствует службы Microsoft 365 и Office 365 и добавляет новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться. Мы рекомендуем вам [подписаться через RSS](https://go.microsoft.com/fwlink/p/?linkid=236301), чтобы получать уведомления при изменении или обновлении этой информации.

Интерфейс звонков и собраний в Teams основан на облачной инфраструктуре следующего поколения, которая также применяется в Skype и Skype для бизнеса. К этим технологиям относятся облачные службы, основанные на Azure, для обработки мультимедийных данных и сигнализации, H. 264 видеокодек, SILK и Opus аудиокодек, устойчивость к сети, телеметрии и диагностики качества. Таким образом, в число требований входят URL- и IP-адреса, которые могут быть сопоставлены как со Skype, так и со Skype для бизнеса.

Для всех рабочих нагрузок Microsoft 365 и Office 365 рекомендуемый способ подключения к службам Teams обходит прокси-сервер пересылки там, где это возможно. Если прокси-сервер находится между клиентом и центрами обработки данных Office 365, мультимедийный трафик может принудительно передаваться по протоколу TCP вместо UDP, что негативно повлияет на качество связи. Скачать образец PAC-файлов, которые можно использовать для настройки пропуска трафика от [управления конечными точками Microsoft 365 и Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).

Если в сети и политиках безопасности требуется трафик Microsoft 365 или Office 365 для передачи через прокси-сервер, перед развертыванием групп в эксплуатацию Убедитесь, что указанные выше требования уже выполнены. Дополнительные сведения можно получить, прочитав [прокси-серверы для Teams или Skype для бизнеса Online](proxy-servers-for-skype-for-business-online.md).
