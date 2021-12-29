---
title: Панель управления — обзор
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: В этой статье представлен обзор новой панели управления.
ms.openlocfilehash: 7def5267b88260b66b6aa345c9585b83659f6ea3
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/29/2021
ms.locfileid: "61625940"
---
# <a name="control-panel"></a>Панель управления

Текущая панель управления — это новая версия устаревшей панели управления, с которой она существует в тандеме. Новая панель управления появилась в накопительном обновлении от июля 2019 г. Он помогает управлять конфигурацией серверов, пользователей, клиентов и устройств в среде организации.

Устаревшая панель управления может не работать, так как 12 октября 2021 г. технология Silverlight достигла стадии "end-of-support". Дополнительные сведения см. в [деле Silverlight End of Support.](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788)

> [!NOTE]
> Сведения о устаревшей панели управления см. в разделе [Панель](../SfbServer/management-tools/install-and-open-administrative-tools.md)управления и перейдите в **раздел Skype для бизнеса Server панели управления.**

## <a name="access-control-panel"></a>Панель управления доступом

Чтобы запустить новую панель управления в браузере, https:// &lt; пул-FQDN/macp или &gt; настроенный простой URL-адрес.

Новая панель управления включает часто используемые элементы меню, которые охватывают большинство потребностей организации. Существует несколько элементов меню из устаревшей панели управления, которые недоступны в новой панели управления. Однако пользователь может использовать функции в этих пунктах меню с помощью cmdlets PowerShell. Дополнительные сведения см. в таблице ниже.

> [!NOTE]
> Документация по другим пунктам меню будет постепенно доступна.

## <a name="client"></a>Клиент

|Sub-menu  |Источник информации для cmdlet  |
|---------|---------|
|Политика версий клиентов         |    [Политика версий клиентов](use-powershell-client-menu.md#client-version-policy)     |
|Конфигурация версий клиентов      |  [Конфигурация версий клиентов](use-powershell-client-menu.md#client-version-configuration)       |
|Обновление устройств    | [Обновление устройств](use-powershell-client-menu.md#device-update)        |
|Тестовое устройство     | [Тестовое устройство](use-powershell-client-menu.md#test-device)        |
|Конфигурация журнала устройств         |    [Конфигурация журнала устройств](use-powershell-client-menu.md#device-log-configuration)     |
|Конфигурация устройств         |    [Конфигурация устройств](use-powershell-client-menu.md#device-configuration)     |
|Политика мобильности         |    [Политика мобильности](use-powershell-client-menu.md#mobility-policy)     |
|Конфигурация push-уведомлений         |    [Конфигурация push-уведомлений](use-powershell-client-menu.md#push-notification-configuration)     |

## <a name="security"></a>Безопасность

|Sub-menu  |Источник информации для cmdlet  |
|---------|---------|
|Регистратор         |    [Регистратор](use-powershell-security-menu.md#registrar)     |
|Веб-служба      |  [Веб-служба](use-powershell-security-menu.md#web-service)       |
|Политика ПИН-кодов    | [Политика ПИН-кодов](use-powershell-security-menu.md#pin-policy)        |

## <a name="im-and-presence"></a>Обмен мгновенными сообщениями и сведениями о присутствии

|Sub-menu  |Источник информации для cmdlet  |
|---------|---------|
|Фильтр файлов         |    [Фильтр файлов](use-powershell-im-and-presence-menu.md#file-filter)     |
|Фильтр URL-адресов      |  [Фильтр URL-адресов](use-powershell-im-and-presence-menu.md#url-filter)       |

## <a name="monitoring-and-archiving"></a>Мониторинг и архивирование

|Sub-menu  |Источник информации для cmdlet  |
|---------|---------|
|Запись сведений о звонке       |    [Запись сведений о звонке](use-powershell-monitoring-and-archiving-menu.md#call-detail-recording)     |
|Качество данных по опыту      |  [Качество данных по опыту](use-powershell-monitoring-and-archiving-menu.md#quality-of-experience-data)       |
|Политика архивирования       |    [Политика архивирования](use-powershell-monitoring-and-archiving-menu.md#archiving-policy)     |
|Конфигурация архивирования      |  [Конфигурация архивирования](use-powershell-monitoring-and-archiving-menu.md#archiving-configuration)       |

## <a name="network-configuration"></a>Конфигурация сети

|Sub-menu  |Источник информации для cmdlet  |
|---------|---------|
|Политика определения местонахождения       |    [Политика расположения](use-powershell-network-configuration-menu.md#location-policy)     |
|Политика пропускной способности      |  [Политика пропускной способности](use-powershell-network-configuration-menu.md#bandwidth-policy)       |
|Регион       |    [Region](use-powershell-network-configuration-menu.md#region)     |
|Site      |  [Site](use-powershell-network-configuration-menu.md#site)       |
|Подсеть      |  [Subnet](use-powershell-network-configuration-menu.md#subnet)       |
|Регион Ссылка       |    [Регион Ссылка](use-powershell-network-configuration-menu.md#region-link)     |
|Маршрут региона      |  [Маршрут региона](use-powershell-network-configuration-menu.md#region-route)       |

## <a name="topology"></a>Топология

|Sub-menu  |Источник информации для cmdlet  |
|---------|---------|
|Состояние       |    [Status](use-powershell-topology-menu.md#status)     |
|Приложение server      |  [Приложение server](use-powershell-topology-menu.md#server-application)       |
|Простой URL-адрес       |    [Простой URL-адрес](use-powershell-topology-menu.md#simple-url)     |
|Надежное приложение       |    [Надежное приложение](use-powershell-topology-menu.md#trusted-application)     |
