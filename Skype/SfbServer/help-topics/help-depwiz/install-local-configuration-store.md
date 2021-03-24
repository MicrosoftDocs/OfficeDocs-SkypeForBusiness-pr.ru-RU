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
description: Чтобы приступить к установке нового сервера ролей Skype для бизнеса Server 2015, сначала необходимо установить локальный SQL Server, на который будет организован локальный магазин конфигураций. Локальный магазин конфигурации будет выступать в качестве только для чтения реплики магазина центра управления Skype для бизнеса Server (CMS). Вы должны войти на сервер, на который запущен этап Install Local Configuration Store в качестве локального администратора на компьютере, и иметь членство в RTCUniversalServerAdmins или группе RTCUniversalGlobalReadOnlyGroup. Если вы выполняете установку на edge Server, вам не нужно быть членом группы RTCUniversalServerAdmins или группы RTCUniversalGlobalReadOnlyGroup. Документ определения topology Builder будет считыт из экспортируемого документа определения, а не из центра управления. Чтобы экспортировать документ определения "Строитель топологии" и сделать его доступным для edge Servers, см. в разделе Экспорт топологии и копирование его на внешние носитли для установки edge.
ms.openlocfilehash: 62a16e441cc95e77aaed7e09152ef2a79221d85f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108745"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="04d1d-108">Установка локального хранилища конфигурации</span><span class="sxs-lookup"><span data-stu-id="04d1d-108">Install Local Configuration Store</span></span>

<span data-ttu-id="04d1d-109">Чтобы приступить к установке нового сервера ролей Skype для бизнеса Server 2015, сначала необходимо установить локальный SQL Server, на который будет организован локальный магазин конфигураций.</span><span class="sxs-lookup"><span data-stu-id="04d1d-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="04d1d-110">Локальный магазин конфигурации будет выступать в качестве только для чтения реплики магазина центра управления Skype для бизнеса Server (CMS).</span><span class="sxs-lookup"><span data-stu-id="04d1d-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="04d1d-111">Вы должны войти на сервер, на который запущен этап Install **Local Configuration Store** в качестве локального администратора на компьютере, и иметь членство в RTCUniversalServerAdmins или группе RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="04d1d-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="04d1d-112">Если вы выполняете установку на edge Server, вам не нужно быть членом группы RTCUniversalServerAdmins или группы RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="04d1d-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="04d1d-113">Документ определения topology Builder будет считыт из экспортируемого документа определения, а не из центра управления.</span><span class="sxs-lookup"><span data-stu-id="04d1d-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="04d1d-114">Чтобы экспортировать документ определения Topology Builder и сделать его доступным для edge Servers, см. в разделе Экспорт топологии и копирование его на внешние носитли для установки [edge.](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)</span><span class="sxs-lookup"><span data-stu-id="04d1d-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span></span>

<span data-ttu-id="04d1d-115">Чтобы приступить к установке:</span><span class="sxs-lookup"><span data-stu-id="04d1d-115">To begin the installation:</span></span>

1. <span data-ttu-id="04d1d-116">На странице Skype для бизнеса Server 2015 рядом с **step1: Install Local Configuration Store** нажмите **кнопку Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="04d1d-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="04d1d-117">На странице **Конфигурация локального** сервера убедитесь, что конфигурация Retrieve автоматически выбрана из параметра **Центральный** магазин управления, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="04d1d-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="04d1d-118">По окончании установки конфигурации локального сервера нажмите кнопку **Finish** (Готово).</span><span class="sxs-lookup"><span data-stu-id="04d1d-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="04d1d-119">Установка локального SQL Server может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="04d1d-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="04d1d-120">Вы не увидите обновлений о ходе работы на сводном экране установки во время SQL Server установки.</span><span class="sxs-lookup"><span data-stu-id="04d1d-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="04d1d-121">Если вы хотите отслеживать ход установки, используйте task Manager для просмотра SQL Server установки.</span><span class="sxs-lookup"><span data-stu-id="04d1d-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>