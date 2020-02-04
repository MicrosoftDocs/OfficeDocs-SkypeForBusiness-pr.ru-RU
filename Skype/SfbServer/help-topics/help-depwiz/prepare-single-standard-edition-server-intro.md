---
title: Подготовка отдельного сервера Standard Edition (введение)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Чтобы начать установку сервера Skype для бизнеса Server 2015 Standard Edition, который будет храниться в хранилище Центрального управления и других размещенных служб, вы должны войти в систему под учетной записью пользователя, который является членом локальной группы администраторов на сервере, который будет Станьте стандартным сервером выпуска. На странице Подготовка сервера Standard Edition вы заданные требования для начальной установки. Компьютер должен входить в домен, в котором вы собираетесь развернуть, и вы должны успешно завершить работу схемы, леса и домена для леса.
ms.openlocfilehash: ed7c353f602d97842e654faa5b539a6dcae01133
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687352"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="5a495-105">Подготовка отдельного сервера Standard Edition (введение)</span><span class="sxs-lookup"><span data-stu-id="5a495-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="5a495-106">Чтобы начать установку сервера Skype для бизнеса Server 2015 Standard Edition, который будет храниться в хранилище Центрального управления и других размещенных служб, вы должны войти в систему под учетной записью пользователя, который является членом локальной группы администраторов на сервере, который будет Станьте стандартным сервером выпуска.</span><span class="sxs-lookup"><span data-stu-id="5a495-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="5a495-107">На странице **Подготовка сервера Standard Edition** вы заданные требования для начальной установки.</span><span class="sxs-lookup"><span data-stu-id="5a495-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="5a495-108">Компьютер должен входить в домен, в котором вы собираетесь развернуть, и вы должны успешно завершить работу схемы, леса и домена для леса.</span><span class="sxs-lookup"><span data-stu-id="5a495-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="5a495-109">Эта конкретная задача предназначена для установки сервера Standard Edition в качестве первого сервера в инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="5a495-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="5a495-110">Эта задача устанавливает центральное хранилище Management (SQL Server Express) на сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5a495-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="5a495-111">Если у вас уже развернут другой сервер Standard Edition или интерфейсный пул, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="5a495-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a495-112">После завершения этой задачи вы сможете установить Topology Builder (если вы еще не установили ее) и настроить документ топологии.</span><span class="sxs-lookup"><span data-stu-id="5a495-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="5a495-113">Опубликовать документ топологии можно только после того, как станет доступным центральное хранилище управления, которое развертывается при завершении задачи, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="5a495-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

