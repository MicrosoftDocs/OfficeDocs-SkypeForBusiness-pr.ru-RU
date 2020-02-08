---
title: URL-адреса и диапазоны IP-адресов для Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Сведения о правильной настройке URL-адресов и диапазонов IP-адресов для Office 365, возможностях обхода прокси-сервера переадресации для соединений со службой Microsoft Teams, а также требованиях к политикам сети и безопасности.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1258138ce6f57dfb0284e030f7a813acf8b94a62
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862799"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URL-адреса и диапазоны IP-адресов для Office 365
=====================================

Перейдите в статью [URL-адреса и диапазоны IP-адресов Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), чтобы просмотреть подробные и актуальные списки URL-адресов, IP-адресов, портов и протоколов, которые нужно настроить правильно для Teams. Корпорация Майкрософт непрерывно совершенствует службу Office 365 и добавляет в нее новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться. Мы рекомендуем вам [подписаться через RSS](https://go.microsoft.com/fwlink/p/?linkid=236301), чтобы получать уведомления при изменении или обновлении этой информации.

Интерфейс звонков и собраний в Teams основан на облачной инфраструктуре следующего поколения, которая также применяется в Skype и Skype для бизнеса. К этим технологиям относятся облачные службы, основанные на Azure, для обработки мультимедийных данных и сигнализации, H. 264 видеокодек, SILK и опус аудиокодек, устойчивость к сети, телеметрии и диагностики качества. Таким образом, в число требований входят URL- и IP-адреса, которые могут быть сопоставлены как со Skype, так и со Skype для бизнеса.

Для всех рабочих нагрузок Office 365 рекомендуемым способом подключения к службам Teams является обход прокси-сервера переадресации, когда это возможно. Если прокси-сервер находится между клиентом и центрами обработки данных Office 365, мультимедийный трафик может принудительно передаваться по протоколу TCP вместо UDP, что негативно повлияет на качество связи. Примеры PAC-файлов прокси-сервера, позволяющие настроить обход трафика, можно скачать в статье [Управление конечными точками Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).

Если в сети и политиках безопасности требуется трафик Office 365 для передачи через прокси-сервер, перед развертыванием групп в рабочей среде убедитесь, что указанные выше требования уже выполнены. Дополнительные сведения можно получить, прочитав [прокси-серверы для Teams или Skype для бизнеса Online](proxy-servers-for-skype-for-business-online.md).
