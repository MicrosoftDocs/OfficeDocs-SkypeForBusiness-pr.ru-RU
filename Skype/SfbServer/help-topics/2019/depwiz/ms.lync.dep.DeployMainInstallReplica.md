---
title: Установка локального хранилища конфигурации
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы приступить к установке нового сервера ролей Skype для бизнеса Server, сначала необходимо установить локальный SQL Server, на который будет организован локальный магазин конфигурации. Локальный магазин конфигурации будет выступать в качестве только для чтения реплики магазина центра управления Skype для бизнеса Server (CMS).
ms.openlocfilehash: 78492f8ce913d8f73336ae4f6cdf06fd340ed5f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095983"
---
# <a name="install-local-configuration-store"></a>Установка локального хранилища конфигурации

Чтобы приступить к установке нового сервера ролей Skype для бизнеса Server, сначала необходимо установить локальный SQL Server, на который будет организован локальный магазин конфигурации. Локальный магазин конфигурации будет выступать в качестве только для чтения реплики магазина центра управления Skype для бизнеса Server (CMS). Вы должны войти на сервер, на который запущен этап Install **Local Configuration Store** в качестве локального администратора на компьютере, и иметь членство в RTCUniversalServerAdmins или группе RTCUniversalGlobalReadOnlyGroup. Если вы выполняете установку на edge Server, вам не нужно быть членом группы RTCUniversalServerAdmins или группы RTCUniversalGlobalReadOnlyGroup. Документ определения topology Builder будет считыт из экспортируемого документа определения, а не из центра управления. Чтобы экспортировать документ определения Topology Builder и сделать его доступным для edge Servers, см. в разделе Экспорт топологии и копирование его на внешние носитли для установки[edge.](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)

Чтобы приступить к установке:

1. На странице Skype для бизнеса Server рядом с **step1: Установите** локальный магазин конфигурации нажмите **кнопку Выполнить**.

2. На странице **Конфигурация локального** сервера убедитесь, что конфигурация Retrieve автоматически выбрана из параметра **Центральный** магазин управления, а затем нажмите **кнопку Далее**.

3. По окончании установки конфигурации локального сервера нажмите кнопку **Finish** (Готово).

> [!NOTE]
> Установка локального SQL Server может занять некоторое время. Вы не увидите обновлений о ходе работы на сводном экране установки во время SQL Server установки. Если вы хотите отслеживать ход установки, используйте task Manager для просмотра SQL Server установки.