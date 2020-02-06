---
title: Установка локального хранилища конфигурации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Чтобы начать установку нового сервера роли Skype для бизнеса Server 2015, необходимо сначала установить локальный сервер SQL Server, на котором будет размещено локальное хранилище конфигураций. Локальное хранилище конфигураций будет использоваться как реплика, предназначенная только для чтения, для хранилища серверов централизованного управления (CMS) Skype для бизнеса Server. На сервер, на котором выполняется шаг Установка локального хранилища конфигурации, вы должны войти как локальный администратор компьютера и участник группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup. При установке пограничного сервера не обязательно быть участником группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup. Документ определения Topology Builder будет прочитан из экспортированного документа, а не из хранилища центрального управления. Чтобы экспортировать документ определения Topology Builder и сделать его доступным для пограничных серверов, ознакомьтесь с разделом экспорт топологии и его копирование на внешние носители для установки пограничного сервера.
ms.openlocfilehash: 7908a862a01871988d6afe6ae1b0cf9c752e9d30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823623"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="26f91-108">Установка локального хранилища конфигурации</span><span class="sxs-lookup"><span data-stu-id="26f91-108">Install Local Configuration Store</span></span>

<span data-ttu-id="26f91-109">Чтобы начать установку нового сервера роли Skype для бизнеса Server 2015, необходимо сначала установить локальный сервер SQL Server, на котором будет размещено локальное хранилище конфигураций.</span><span class="sxs-lookup"><span data-stu-id="26f91-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="26f91-110">Локальное хранилище конфигураций будет использоваться как реплика, предназначенная только для чтения, для хранилища серверов централизованного управления (CMS) Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="26f91-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="26f91-111">На сервер, на котором выполняется шаг **Установка локального хранилища конфигурации**, вы должны войти как локальный администратор компьютера и участник группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="26f91-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="26f91-112">При установке пограничного сервера не обязательно быть участником группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="26f91-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="26f91-113">Документ определения Topology Builder будет прочитан из экспортированного документа, а не из хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="26f91-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="26f91-114">Чтобы экспортировать документ определения Topology Builder и сделать его доступным для пограничных серверов, ознакомьтесь с разделом [Экспорт топологии и его копирование на внешние носители для установки пограничного](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)сервера.</span><span class="sxs-lookup"><span data-stu-id="26f91-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="26f91-115">Чтобы начать установку, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="26f91-115">To begin the installation:</span></span>

1. <span data-ttu-id="26f91-116">На странице Skype для бизнеса Server 2015 рядом с **Step1: установите локальное хранилище конфигураций**, нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="26f91-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="26f91-117">На странице **Конфигурация локального сервера** убедитесь, что установлен флажок **Получить непосредственно из центрального хранилища управления**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="26f91-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="26f91-118">По окончании установки конфигурации локального сервера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="26f91-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="26f91-119">Установка локального сервера SQL Server может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="26f91-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="26f91-120">При установке SQL Server на экране сводки установки не отображаются обновления.</span><span class="sxs-lookup"><span data-stu-id="26f91-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="26f91-121">Если вы хотите отслеживать ход выполнения установки, используйте диспетчер задач для просмотра настроек SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26f91-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


