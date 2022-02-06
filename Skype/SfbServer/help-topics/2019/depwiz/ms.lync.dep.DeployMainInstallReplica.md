---
title: Установка локального хранилища конфигурации
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Чтобы приступить к установке нового сервера Skype для бизнеса Server ролей, сначала необходимо установить локальный SQL Server, в который будет храниться локализованная конфигурация. Локальный магазин конфигурации будет выступать в качестве только для чтения реплики Skype для бизнеса Server центрального магазина управления (CMS).'
---

# <a name="install-local-configuration-store"></a>Установка локального хранилища конфигурации

Чтобы приступить к установке нового сервера Skype для бизнеса Server ролей, сначала необходимо установить локальный SQL Server, в который будет храниться локализованная конфигурация. Локальный магазин конфигурации будет выступать в качестве только для чтения реплики Skype для бизнеса Server центрального магазина управления (CMS). Вы должны войти на сервер, на который запущен этап Install **Local Configuration Store** в качестве локального администратора на компьютере, и иметь членство в RTCUniversalServerAdmins или группе RTCUniversalGlobalReadOnlyGroup. Если вы выполняете установку на edge Server, вам не нужно быть членом группы RTCUniversalServerAdmins или группы RTCUniversalGlobalReadOnlyGroup. Документ определения topology Builder будет считыт из экспортируемого документа определения, а не из центра управления. Чтобы экспортировать документ определения Topology Builder и сделать его доступным для edge Servers, см. в [разделеExport Your Topology и Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).

Чтобы приступить к установке:

1. На странице Skype для бизнеса Server рядом с **step1: Установите локальный** магазин конфигурации нажмите **кнопку Выполнить**.

2. На странице **Конфигурация локального** сервера убедитесь, что конфигурация Retrieve автоматически выбрана из параметра **Центра** управления магазином, а затем нажмите **кнопку Далее**.

3. По окончании установки конфигурации локального сервера нажмите кнопку **Finish** (Готово).

> [!NOTE]
> Установка локальной SQL Server может занять некоторое время. При установке SQL Server обновления на экране сводки установки не будут видеться. Если вы хотите отслеживать ход установки, используйте task Manager для просмотра SQL Server установки.