---
title: Установка локального хранилища конфигурации
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Чтобы начать установку новых Скайп для роли сервера Business Server, необходимо сначала установить на локальном SQL Server, на котором будет размещаться локального хранилища конфигурации. Локальное хранилище конфигурации будет действовать как только для чтения реплики Скайп для бизнеса сервера центрального хранилища управления (CMS). Необходимо войти в систему на сервере выполняются на этапе установки локального хранилища конфигурации учетной записью локального администратора на компьютере и иметь членство в группе RTCUniversalServerAdmins или группе групп RTCUniversalGlobalReadOnlyGroup. При установке пограничного сервера не обязательно быть участником группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup. Документ описания Topology Builder считываются из документа экспортированного определения а не из центрального хранилища управления. Чтобы экспортировать документ описания Topology Builder и сделать его доступным для пограничных серверов, см раздел Экспорт Your Topology и копировать его на внешний носитель для установки пограничного сервера.
ms.openlocfilehash: fd2e6a51d0ff7d6194f0ec39592765807ea55da4
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988301"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="cbc09-108">Установка локального хранилища конфигурации</span><span class="sxs-lookup"><span data-stu-id="cbc09-108">Install Local Configuration Store</span></span>
 
<span data-ttu-id="cbc09-109">Чтобы начать установку новых Скайп для роли сервера Business Server, необходимо сначала установить на локальном SQL Server, на котором будет размещаться локального хранилища конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cbc09-109">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="cbc09-110">Локальное хранилище конфигурации будет действовать как только для чтения реплики Скайп для бизнеса сервера центрального хранилища управления (CMS).</span><span class="sxs-lookup"><span data-stu-id="cbc09-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="cbc09-111">На сервер, на котором выполняется шаг **Установка локального хранилища конфигурации**, вы должны войти как локальный администратор компьютера и участник группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="cbc09-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="cbc09-112">При установке пограничного сервера не обязательно быть участником группы RTCUniversalServerAdmins или RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="cbc09-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="cbc09-113">Документ описания Topology Builder считываются из документа экспортированного определения а не из центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="cbc09-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="cbc09-114">Чтобы экспортировать документ описания Topology Builder и сделать его доступным для пограничных серверов, приведены в разделе[Экспорт Your Topology и копировать его на внешние носители для установки пограничного сервера](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="cbc09-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>
  
<span data-ttu-id="cbc09-115">Чтобы начать установку, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="cbc09-115">To begin the installation:</span></span>
  
1. <span data-ttu-id="cbc09-116">На Скайп для страницы Business Server рядом с элементом **Шаг 1: Установка локального хранилища конфигурации**, выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="cbc09-116">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>
    
2. <span data-ttu-id="cbc09-117">На странице **Конфигурация локального сервера** убедитесь, что установлен флажок **Получить непосредственно из центрального хранилища управления**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cbc09-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>
    
3. <span data-ttu-id="cbc09-118">По окончании установки конфигурации локального сервера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="cbc09-118">When the local server configuration installation is complete, click **Finish**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cbc09-119">Установка локального сервера SQL может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="cbc09-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="cbc09-120">Не появится обновлений о ходе выполнения в окне сводки установки во время установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cbc09-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="cbc09-121">Для проверки хода выполнения установки, используйте диспетчер задач для просмотра установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cbc09-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span> 
  

