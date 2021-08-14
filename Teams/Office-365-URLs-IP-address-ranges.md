---
title: Microsoft 365 и Office 365 URL-адреса и диапазоны IP-адресов
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Узнайте, как правильно настроить Microsoft 365 или Office 365 URL-адреса и диапазоны IP-адресов и обойти прокси-сервер по возможности для подключений к Microsoft Teams службе.
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
ms.openlocfilehash: 9d0a1270d621c61fc224bbc799f1007ef9818542
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2021
ms.locfileid: "58233884"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 и Office 365 URL-адреса и диапазоны IP-адресов

Подробный [список URL-адресов,](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) IP-адресов, IP-адресов, портов и протоколов, которые необходимо правильно настроить для Teams, можно найти в Microsoft 365 и Office 365 URL-адреса и диапазоны IP-Teams. Корпорация Майкрософт непрерывно совершенствует службы Microsoft 365 и Office 365 и добавляет новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться. Мы рекомендуем подписаться [на RSS-канал,](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) чтобы получать уведомления об обновлении или смене данных.

Вызовы Teams собраниями основаны на облачной инфраструктуре нового поколения, которая также используется Skype и Skype для бизнеса. К этим технологиям относятся облачные службы на базе Azure для обработки мультимедиа и сигнального сигнала, видеокодек H.264, аудиокодек SILK и Opus, устойчивость сети, телеметрия и диагностика качества. Поэтому существуют URL-адреса и URL-адреса, которые могут быть связаны как с Skype, так и Skype для бизнеса.

Для всех рабочих Microsoft 365 и Office 365, рекомендуемый способ подключения к Teams службам — обход прокси-сервера, если это возможно. Если прокси-сервер находится между клиентом и Office 365 центрами обработки данных, мультимедиа могут быть принудительными к TCP, а не UDP, что повлияет на качество мультимедиа. Скачайте образцы PAC-файлов прокси-сервера, которые можно использовать для настройки обхода трафика в Microsoft 365 и [Office 365 конечных точек.](/office365/enterprise/managing-office-365-endpoints)

Если для сетевых политик и политик безопасности требуется Microsoft 365 или Office 365 трафик для прокси-сервера, убедитесь, что эти требования уже выполнены, прежде чем Teams в производственной сфере. Дополнительные сведения о [прокси-серверах для Teams или Skype для бизнеса Online.](proxy-servers-for-skype-for-business-online.md)