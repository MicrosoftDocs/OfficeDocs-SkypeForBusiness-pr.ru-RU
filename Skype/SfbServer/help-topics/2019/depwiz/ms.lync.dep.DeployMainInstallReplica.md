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
description: Чтобы начать установку нового сервера роли Skype для бизнеса Server, необходимо сначала установить локальный сервер SQL Server на который будет храниться локальное хранилище конфигурации. Локальное хранилище конфигурации будет выступать в качестве реплики центрального управления (CMS) Skype для бизнеса Server, доступной только для чтения.
ms.openlocfilehash: dcaf00e0bd14daecb6d2859bf40463265a3d6bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833809"
---
# <a name="install-local-configuration-store"></a>Установка локального хранилища конфигурации

Чтобы начать установку нового сервера роли Skype для бизнеса Server, необходимо сначала установить локальный сервер SQL Server на который будет храниться локальное хранилище конфигурации. Локальное хранилище конфигурации будет выступать в качестве реплики центрального управления (CMS) Skype для бизнеса Server, доступной только для чтения. Необходимо войти в систему на сервере,  где запущен этап установки локального магазина конфигурации, в качестве локального администратора на компьютере и иметь членство в группе RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup. При выполнении установки на edge Server не нужно быть членом группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup. Документ определения построитель топологий будет считын из экспортируемого документа определения, а не из центрального хранилище управления. Чтобы экспортировать документ определения построитель топологий и сделать его доступным для edge-серверов, см. раздел "Экспорт топологии и копирование на внешние носиты для установки по[краям".](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)

Чтобы начать установку:

1. On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.

2. На странице **"Конфигурация** локального  сервера" убедитесь, что выбран параметр "Извлечь конфигурацию автоматически из центрального банка управления" и нажмите кнопку **"Далее".**

3. По окончании установки конфигурации локального сервера нажмите кнопку **Finish** (Готово).

> [!NOTE]
> Установка локального SQL Server может занять некоторое время. Обновления на экране сводки установки не будут обновлены во время SQL Server установки. Если вы хотите отслеживать ход выполнения установки, используйте диспетчер задач для наблюдения за SQL Server установки.


