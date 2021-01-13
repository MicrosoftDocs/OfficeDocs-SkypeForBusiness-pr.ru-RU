---
title: Установка локального хранилища конфигурации
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Чтобы начать установку нового сервера ролей Skype для бизнеса Server 2015, необходимо сначала установить локальный сервер SQL Server, на который будет храниться локальное хранилище конфигурации. Локальное хранилище конфигурации будет выступать в качестве реплики центрального управления (CMS) Skype для бизнеса Server, доступной только для чтения. Необходимо войти в систему на сервере, где запущен этап установки локального магазина конфигурации, в качестве локального администратора на компьютере и иметь членство в группе RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup. При выполнении установки на edge Server не нужно быть членом группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup. Документ определения построитель топологий будет считын из экспортируемого документа определения, а не из центрального хранилище управления. Чтобы экспортировать документ определения построитель топологий и сделать его доступным для edge-серверов, см. раздел "Экспорт топологии и копирование на внешние носитли для установки по краям".
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827149"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="36ab0-108">Установка локального хранилища конфигурации</span><span class="sxs-lookup"><span data-stu-id="36ab0-108">Install Local Configuration Store</span></span>

<span data-ttu-id="36ab0-109">Чтобы начать установку нового сервера ролей Skype для бизнеса Server 2015, необходимо сначала установить локальный сервер SQL Server, на который будет храниться локальное хранилище конфигурации.</span><span class="sxs-lookup"><span data-stu-id="36ab0-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="36ab0-110">Локальное хранилище конфигурации будет выступать в качестве реплики центрального управления (CMS) Skype для бизнеса Server, доступной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="36ab0-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="36ab0-111">Необходимо войти в систему на сервере,  где запущен этап установки локального магазина конфигурации, в качестве локального администратора на компьютере и иметь членство в группе RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="36ab0-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="36ab0-112">При выполнении установки на edge Server не нужно быть членом группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="36ab0-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="36ab0-113">Документ определения построитель топологий будет считын из экспортируемого документа определения, а не из центрального хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="36ab0-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="36ab0-114">Чтобы экспортировать документ определения построитель топологий и сделать его доступным для edge-серверов, см. раздел "Экспорт топологии и копирование на внешние носиты для установки по [краям".](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)</span><span class="sxs-lookup"><span data-stu-id="36ab0-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="36ab0-115">Чтобы начать установку:</span><span class="sxs-lookup"><span data-stu-id="36ab0-115">To begin the installation:</span></span>

1. <span data-ttu-id="36ab0-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span><span class="sxs-lookup"><span data-stu-id="36ab0-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="36ab0-117">На странице **"Конфигурация** локального  сервера" убедитесь, что выбран параметр "Извлечь конфигурацию автоматически из центрального банка управления" и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="36ab0-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="36ab0-118">По окончании установки конфигурации локального сервера нажмите кнопку **Finish** (Готово).</span><span class="sxs-lookup"><span data-stu-id="36ab0-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="36ab0-119">Установка локального SQL Server может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="36ab0-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="36ab0-120">Обновления на экране сводки установки не будут обновлены во время SQL Server установки.</span><span class="sxs-lookup"><span data-stu-id="36ab0-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="36ab0-121">Если вы хотите отслеживать ход выполнения установки, используйте диспетчер задач для наблюдения за SQL Server установки.</span><span class="sxs-lookup"><span data-stu-id="36ab0-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


