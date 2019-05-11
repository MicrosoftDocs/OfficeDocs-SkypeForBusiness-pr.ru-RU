---
title: Установка локального хранилища конфигурации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы начать установку новых Скайп для роли сервера Business Server, необходимо сначала установить на локальном SQL Server, на котором будет размещаться локального хранилища конфигурации. Локальное хранилище конфигурации будет действовать как только для чтения реплики Скайп для бизнеса сервера центрального хранилища управления (CMS).
ms.openlocfilehash: 5fddc31ac297a6938d242936afcd00ddb3d9fbf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893674"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="26f0d-104">Установка локального хранилища конфигурации</span><span class="sxs-lookup"><span data-stu-id="26f0d-104">Install Local Configuration Store</span></span>

<span data-ttu-id="26f0d-105">Чтобы начать установку новых Скайп для роли сервера Business Server, необходимо сначала установить на локальном SQL Server, на котором будет размещаться локального хранилища конфигурации.</span><span class="sxs-lookup"><span data-stu-id="26f0d-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="26f0d-106">Локальное хранилище конфигурации будет действовать как только для чтения реплики Скайп для бизнеса сервера центрального хранилища управления (CMS).</span><span class="sxs-lookup"><span data-stu-id="26f0d-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="26f0d-107">На сервер, на котором выполняется шаг **Установка локального хранилища конфигурации**, вы должны войти как локальный администратор компьютера и участник группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="26f0d-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="26f0d-108">При установке пограничного сервера не обязательно быть участником группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="26f0d-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="26f0d-109">Документ описания Topology Builder считываются из документа экспортированного определения а не из центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="26f0d-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="26f0d-110">Чтобы экспортировать документ описания Topology Builder и сделать его доступным для пограничных серверов, приведены в разделе[Экспорт Your Topology и копировать его на внешние носители для установки пограничного сервера](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="26f0d-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="26f0d-111">Чтобы начать установку, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="26f0d-111">To begin the installation:</span></span>

1. <span data-ttu-id="26f0d-112">На Скайп для страницы Business Server рядом с элементом **Шаг 1: Установка локального хранилища конфигурации**, выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="26f0d-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="26f0d-113">На странице **Конфигурация локального сервера** убедитесь, что установлен флажок **Получить непосредственно из центрального хранилища управления**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="26f0d-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="26f0d-114">По окончании установки конфигурации локального сервера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="26f0d-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="26f0d-115">Установка локального сервера SQL может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="26f0d-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="26f0d-116">Не появится обновлений о ходе выполнения в окне сводки установки во время установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26f0d-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="26f0d-117">Для проверки хода выполнения установки, используйте диспетчер задач для просмотра установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26f0d-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


