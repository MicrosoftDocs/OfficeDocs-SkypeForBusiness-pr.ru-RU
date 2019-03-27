---
title: Подготовка отдельного сервера Standard Edition (введение)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы начать установку Скайп для сервера Business Server Standard Edition, который будет содержать центральное хранилище управления и других выровненных служб, которые можно выбрать, необходимо войти качестве должна быть членом локальной группы администраторов на сервере, который станет сервер Standard Edition. Странице Prepare один стандартный выпуск сервера подробно описываются требования к начальной установки. Компьютер должен быть членом домена, в котором планируется развернуть его, и необходимо успешно выполнить Подготовка схемы, домена и леса для своего леса.
ms.openlocfilehash: b4b211899ba907a20d11f8adf4d2640599dc6f91
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883653"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="672ce-105">Подготовка отдельного сервера Standard Edition (введение)</span><span class="sxs-lookup"><span data-stu-id="672ce-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="672ce-106">Чтобы начать установку Скайп для сервера Business Server Standard Edition, который будет содержать центральное хранилище управления и других выровненных служб, которые можно выбрать, необходимо войти качестве должна быть членом локальной группы администраторов на сервере, который станет сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="672ce-106">To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="672ce-107">На странице **Prepare один стандартный выпуск сервера** подробно описывает требования для первоначальной установки.</span><span class="sxs-lookup"><span data-stu-id="672ce-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="672ce-108">Компьютер должен быть членом домена, в котором планируется развернуть его, и необходимо успешно выполнить Подготовка схемы, домена и леса для своего леса.</span><span class="sxs-lookup"><span data-stu-id="672ce-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="672ce-109">Эта конкретная задача предназначена для установки сервера Standard Edition в качестве первого сервера в инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="672ce-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="672ce-110">Эта задача устанавливает центрального хранилища управления, который является SQL Server Express на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="672ce-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="672ce-111">Если у вас уже развернут другой сервер Standard Edition или интерфейсный пул, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="672ce-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="672ce-112">После завершения этой задачи, будет установка Topology Builder (Если вы еще не установили его) и Настройка топологии документа.</span><span class="sxs-lookup"><span data-stu-id="672ce-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="672ce-113">Опубликовать документ топологии можно только после того, как станет доступным центральное хранилище управления, которое развертывается при завершении задачи, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="672ce-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

