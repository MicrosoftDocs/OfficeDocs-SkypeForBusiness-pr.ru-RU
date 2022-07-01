---
title: URL-адреса и диапазоны IP Office 365 Microsoft 365 и Office 365 ip-адресов
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Узнайте, как правильно настроить URL-адреса и диапазоны IP-Office 365 Microsoft 365 или Office 365 и по возможности обойти прокси-сервер пересылки для подключений к службе Microsoft Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: e2f638b9fb29c80806082e02f2d0b09ceec619d0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563737"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL-адреса и диапазоны IP Office 365 Microsoft 365 и Office 365 ip-адресов

Чтобы получить подробный и актуальный список URL-адресов, IP-адресов, портов и протоколов, которые должны быть правильно настроены для Teams, перейдите по URL-адресам и [Office 365 Microsoft 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) и Office 365 IP-адресов. Корпорация Майкрософт непрерывно совершенствует службы Microsoft 365 и Office 365 и добавляет новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться. Мы рекомендуем подписаться [через RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) для получения уведомлений при обновлении или изменении этой информации.

Интерфейс звонков и собраний Teams основан на облачной инфраструктуре следующего поколения, которая также используется Skype и Skype для бизнеса. Эти инвестиции в технологии включают облачные службы на основе Azure для обработки и передачи сигналов мультимедиа, видеоко кодека H.264, аудиококока SILK и Opus, отказоустойчивость сети, телеметрию и диагностику качества. Таким образом, требуются URL-адреса и IP-адреса, которые могут быть связаны со Skype и Skype для бизнеса.

Для всех рабочих нагрузок Microsoft 365 Office 365 microsoft 365 рекомендуемый метод подключения к службам Teams по возможности обходит прямой прокси-сервер. Если прокси-сервер находится между клиентом и центром обработки Office 365 данных, носитель может быть принудительно подключен по протоколу TCP, а не по протоколу UDP, что повлияет на качество мультимедиа. Скачайте примеры PAC-файлов прокси-сервера, которые можно использовать для настройки обхода трафика из службы управления [Microsoft 365 и Office 365 конечных точек](/office365/enterprise/managing-office-365-endpoints).

Если политикам сети и безопасности требуется трафик Microsoft 365 или Office 365 для передачи через прокси-сервер, убедитесь, что указанные выше требования уже выполнены перед развертыванием Teams в рабочей области. Дополнительные сведения см. на [прокси-серверах для Teams или Skype для бизнеса Online](proxy-servers-for-skype-for-business-online.md).