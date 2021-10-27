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
ms.openlocfilehash: 8a4f8e073b424969951a69c620dd5f65a582fd75
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579997"
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

## <a name="client"></a>Client

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