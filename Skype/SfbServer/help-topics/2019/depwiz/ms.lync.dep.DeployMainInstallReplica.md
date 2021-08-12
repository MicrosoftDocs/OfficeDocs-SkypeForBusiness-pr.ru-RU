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
description: Чтобы приступить к установке нового сервера Skype для бизнеса Server ролей, сначала необходимо установить локальный SQL Server, в который будет храниться локализованная конфигурация. Локальный магазин конфигурации будет выступать в качестве только для чтения реплики Skype для бизнеса Server центрального магазина управления (CMS).
ms.openlocfilehash: 96dc427ddcc1ed2716033e30747006afc9947bf813dd6287fdcc734270993c96
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340135"
---
# <a name="install-local-configuration-store"></a>Установка локального хранилища конфигурации

Чтобы приступить к установке нового сервера Skype для бизнеса Server ролей, сначала необходимо установить локальный SQL Server, в который будет храниться локализованная конфигурация. Локальный магазин конфигурации будет выступать в качестве только для чтения реплики Skype для бизнеса Server центрального магазина управления (CMS). Вы должны войти на сервер, на который запущен этап Install **Local Configuration Store** в качестве локального администратора на компьютере, и иметь членство в RTCUniversalServerAdmins или группе RTCUniversalGlobalReadOnlyGroup. Если вы выполняете установку на edge Server, вам не нужно быть членом группы RTCUniversalServerAdmins или группы RTCUniversalGlobalReadOnlyGroup. Документ определения topology Builder будет считыт из экспортируемого документа определения, а не из центра управления. Чтобы экспортировать документ определения Topology Builder и сделать его доступным для edge Servers, см. в разделе Экспорт топологии и копирование его на внешние носитли для установки[edge.](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)

Чтобы приступить к установке:

1. На странице Skype для бизнеса Server, рядом с **step1: Установите локальный** магазин конфигурации , нажмите **кнопку Выполнить**.

2. На странице **Конфигурация локального** сервера убедитесь, что конфигурация Retrieve автоматически выбрана из параметра **Центральный** магазин управления, а затем нажмите **кнопку Далее**.

3. По окончании установки конфигурации локального сервера нажмите кнопку **Finish** (Готово).

> [!NOTE]
> Установка локальной SQL Server может занять некоторое время. При установке SQL Server обновления на экране сводки установки не будут видеться. Если вы хотите отслеживать ход установки, используйте task Manager для просмотра SQL Server установки.