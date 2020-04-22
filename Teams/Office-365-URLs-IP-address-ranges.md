---
title: URL-адреса и диапазоны IP-адресов для Microsoft 365 и Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Сведения о том, как правильно настроить URL-адреса и диапазоны IP-адресов для Office 365 и обойти прокси-сервер переадресации для подключений к службе Microsoft Teams.
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
ms.openlocfilehash: 635ec9007e4cb4742b9076b15b89d32ad77a135f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778625"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL-адреса и диапазоны IP-адресов для Microsoft 365 и Office 365
=======================================================

Перейдите на [URL-адреса и диапазоны IP-адресов для microsoft 365 и Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) , чтобы получить подробный и актуальный список URL-адресов, IP-адресов, портов и протоколов, которые должны быть правильно настроены для Teams. Корпорация Майкрософт непрерывно совершенствует службу Office 365 и добавляет в нее новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться. Мы рекомендуем вам [подписаться через RSS](https://go.microsoft.com/fwlink/p/?linkid=236301), чтобы получать уведомления при изменении или обновлении этой информации.

Интерфейс звонков и собраний в Teams основан на облачной инфраструктуре следующего поколения, которая также применяется в Skype и Skype для бизнеса. К этим технологиям относятся облачные службы, основанные на Azure, для обработки мультимедийных данных и сигнализации, H. 264 видеокодек, SILK и Opus аудиокодек, устойчивость к сети, телеметрии и диагностики качества. Таким образом, в число требований входят URL- и IP-адреса, которые могут быть сопоставлены как со Skype, так и со Skype для бизнеса.

Для всех рабочих нагрузок Office 365 рекомендуемым способом подключения к службам Teams является обход прокси-сервера переадресации, когда это возможно. Если прокси-сервер находится между клиентом и центрами обработки данных Office 365, мультимедийный трафик может принудительно передаваться по протоколу TCP вместо UDP, что негативно повлияет на качество связи. Скачать образец PAC-файлов, которые можно использовать для настройки пропуска трафика от [управления конечными точками Microsoft 365 и Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).

Если в сети и политиках безопасности требуется трафик Office 365 для передачи через прокси-сервер, перед развертыванием групп в рабочей среде убедитесь, что указанные выше требования уже выполнены. Дополнительные сведения можно получить, прочитав [прокси-серверы для Teams или Skype для бизнеса Online](proxy-servers-for-skype-for-business-online.md).
