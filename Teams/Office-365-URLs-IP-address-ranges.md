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
description: Узнайте, как правильно настроить URL-адреса и диапазоны IP-адресов Microsoft 365 или Office 365, а также настроить обход прокси-сервера, если это возможно, для подключений к службе Microsoft Teams.
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
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094521"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL-адреса и диапазоны IP-адресов Microsoft 365 и Office 365
=======================================================

Перейдите на URL-адреса и диапазоны IP-адресов [Microsoft 365 и Office 365,](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) чтобы получить подробный и новый список URL-адресов, IP-адресов, портов и протоколов, которые необходимо правильно настроить для Teams. Корпорация Майкрософт непрерывно совершенствует службы Microsoft 365 и Office 365 и добавляет новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться. Мы рекомендуем подписаться [с помощью RSS,](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) чтобы получать уведомления об обновлениях или изменениях этой информации.

Вызовы и собрания Teams основаны на облачной инфраструктуре нового поколения, которая также используется Skype и Skype для бизнеса. Эти технологии включают облачные службы на базе Azure для обработки мультимедиа и сигнального сигнала, видеокодек H.264, аудиокодек SILK и Opus, устойчивость сети, телеметрию и диагностику качества. Поэтому существуют URL-адреса и IPS, которые могут быть связаны как со Skype, так и со Skype для бизнеса.

Для всех рабочих нагрузок Microsoft 365 и Office 365 рекомендуемый способ подключения к службам Teams по возможности обходит перенаский прокси-сервер. Когда прокси-сервер находится между клиентом и центрами обработки данных Office 365, мультимедиа могут быть принудительными через TCP, а не UDP, что повлияет на качество мультимедиа. Скачайте образцы PAC-файлов прокси-сервера, которые можно использовать для настройки обхода трафика для управления конечными точками [Microsoft 365 и Office 365.](/office365/enterprise/managing-office-365-endpoints)

Если для сетевых политик и политик безопасности требуется трафик Microsoft 365 или Office 365 для прокси-сервера, перед развертыванием Teams в производственной сфере убедитесь, что эти требования уже выполнены. Дополнительные сведения можно получить на [прокси-серверах для Teams или Skype для бизнеса Online.](proxy-servers-for-skype-for-business-online.md)