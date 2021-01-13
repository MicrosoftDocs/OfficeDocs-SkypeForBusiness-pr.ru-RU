---
title: Проверка репликации раздела леса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Чтобы проверить успешность репликации глобального каталога и создания объектов в ходе подготовки леса, сделайте следующее:'
ms.openlocfilehash: 010cf3fbadf8e07b4ccb80c33c34057024dde896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800559"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="ed6cf-103">Проверка репликации раздела леса</span><span class="sxs-lookup"><span data-stu-id="ed6cf-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="ed6cf-104">Чтобы проверить успешность репликации глобального каталога и создания объектов в ходе подготовки леса, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ed6cf-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="ed6cf-105">На контроллере домена (желательно в месте, удаленном от других контроллеров домена) в лесу, для которого выполнялась подготовка, откройте окно **Active Directory — пользователи и компьютеры**.</span><span class="sxs-lookup"><span data-stu-id="ed6cf-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="ed6cf-106">В окне **Active Directory — пользователи и компьютеры** разверните имя домена своего леса или дочернего домена.</span><span class="sxs-lookup"><span data-stu-id="ed6cf-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="ed6cf-107">Щелкните **контейнер Users** в левой области и найдите универсальную группу CsAdministrator в правой области.</span><span class="sxs-lookup"><span data-stu-id="ed6cf-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="ed6cf-108">Если присутствует CsAdministrator (среди восьми других новых универсальных групп, которые начинаются с Cs), репликация подготовки леса была успешной.</span><span class="sxs-lookup"><span data-stu-id="ed6cf-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="ed6cf-p102">Если группа или группы отсутствуют, вы можете принудительно ускорить выполнение репликации или подождать 15 минут и затем обновить правую панель. Если группы появились, репликация завершена.</span><span class="sxs-lookup"><span data-stu-id="ed6cf-p102">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane. When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="ed6cf-111">Если вы хотите просмотреть файлы журналов, созданные мастером развертывания Skype для бизнеса Server, их можно найти на компьютере, на котором был развернут мастер развертывания, в каталоге Users пользователя доменных служб Active Directory, который запустил этот шаг.</span><span class="sxs-lookup"><span data-stu-id="ed6cf-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="ed6cf-112">Например, если пользователь вошел с учетной записью администратора домена в домене Contoso.net, файлы журнала будут расположены в папке C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="ed6cf-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

