---
title: Подготовка отдельного сервера Standard Edition (введение)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server. На странице "Подготовка одного сервера Standard Edition" подробно приводится информация о требованиях к начальной установке. Компьютер должен быть членом домена, в котором он будет развернут, и необходимо успешно завершить подготовку схемы, леса и домена для леса.
ms.openlocfilehash: 08ea84c0d136339e782c32785c1c4fb536f877cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820629"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="30267-105">Подготовка отдельного сервера Standard Edition (введение)</span><span class="sxs-lookup"><span data-stu-id="30267-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="30267-106">To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span><span class="sxs-lookup"><span data-stu-id="30267-106">To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="30267-107">На **странице "Подготовка одного сервера Standard Edition"** подробно приводится информация о требованиях к начальной установке.</span><span class="sxs-lookup"><span data-stu-id="30267-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="30267-108">Компьютер должен быть членом домена, в котором он будет развернут, и необходимо успешно завершить подготовку к схеме, лесу и домену для леса.</span><span class="sxs-lookup"><span data-stu-id="30267-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="30267-109">Эта конкретная задача предназначена для установки сервера Standard Edition в качестве первого сервера в инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="30267-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="30267-110">Эта задача устанавливает центральное хранилище управления, которое SQL Server Express, на сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="30267-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="30267-111">Если у вас уже развернут другой сервер Standard Edition или интерфейсный пул, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="30267-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="30267-112">После выполнения этой задачи необходимо установить построитель топологий (если он еще не установлен) и настроить документ топологии.</span><span class="sxs-lookup"><span data-stu-id="30267-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="30267-113">Опубликовать документ топологии можно только после того, как станет доступным центральное хранилище управления, которое развертывается при завершении задачи, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="30267-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

