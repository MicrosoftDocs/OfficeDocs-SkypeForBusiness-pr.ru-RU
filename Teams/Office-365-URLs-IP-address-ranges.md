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
description: Узнайте, как правильно настроить Microsoft 365 или Office 365 URL-адреса и диапазоны IP-адресов и обходить прокси-сервер пересылки по возможности для подключений Microsoft Teams службы.
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
ms.openlocfilehash: 1ebcf7c6595da3e1774571be4c65a796838115b3
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675721"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 и Office 365 URL-адреса и диапазоны IP-адресов

Подробный и актуальный список [URL-адресов, IP-адресов, IP-адресов](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), портов и протоколов, которые должны быть правильно настроены для Teams, см. в Microsoft 365 и Office 365 URL-адресах и диапазонах IP-адресов. Корпорация Майкрософт непрерывно совершенствует службы Microsoft 365 и Office 365 и добавляет новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться. Мы рекомендуем подписаться [через RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) для получения уведомлений при обновлении или изменении этой информации.

Интерфейс Teams и собраний основан на облачной инфраструктуре нового поколения, которая также используется Skype и Skype для бизнеса. Эти инвестиции в технологии включают облачные службы на основе Azure для обработки и передачи сигналов мультимедиа, видеоко кодека H.264, аудиококока SILK и Opus, отказоустойчивость сети, телеметрию и диагностику качества. Таким образом, требуются URL-адреса и IP-адреса, которые могут быть связаны Skype и Skype для бизнеса.

Для всех Microsoft 365 и Office 365 рабочих нагрузок рекомендуемый метод подключения к Teams службы обходит прокси-сервер переадресации, где это возможно. Если прокси-сервер находится между клиентом и центром обработки Office 365 данных, носитель может быть принудительно подключен по протоколу TCP, а не по протоколу UDP, что повлияет на качество мультимедиа. Скачайте примеры PAC-файлов прокси-сервера, которые можно использовать для настройки обхода трафика из Microsoft 365 и Office 365 [конечных точек](/office365/enterprise/managing-office-365-endpoints).

Если для сетевых политик и политик безопасности требуется Microsoft 365 или Office 365 трафик для передачи через прокси-сервер, убедитесь, что указанные выше требования уже выполнены перед развертыванием Teams в рабочей области. Дополнительные сведения см. на [прокси-серверах Teams или Skype для бизнеса Online](proxy-servers-for-skype-for-business-online.md).