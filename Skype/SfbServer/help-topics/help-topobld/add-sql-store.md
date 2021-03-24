---
title: Добавление хранилища SQL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: Чтобы определить новый SQL Store, это означает, что для SQL Server базы данных и экземпляра SQL Server — экземпляр по умолчанию или именуемого экземпляра — укажите следующее.
ms.openlocfilehash: 28018a7320bc42761a668aaff385302016781592
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095603"
---
# <a name="add-sql-store"></a><span data-ttu-id="448fe-103">Добавление хранилища SQL</span><span class="sxs-lookup"><span data-stu-id="448fe-103">Add SQL Store</span></span>

<span data-ttu-id="448fe-104">Чтобы определить новый SQL Store, это означает, что для SQL Server базы данных и экземпляра SQL Server — экземпляр по умолчанию или именуемого экземпляра — укажите следующее.</span><span class="sxs-lookup"><span data-stu-id="448fe-104">To define a new SQL Store, which means that you are specifying a SQL Server-based database and an instance of SQL Server—either a default instance or a named instance—you specify the following.</span></span>

<span data-ttu-id="448fe-105">Укажите полное доменное имя (FQDN) SQL Server, в которой будет баз данных экземпляр, который вы определяете.</span><span class="sxs-lookup"><span data-stu-id="448fe-105">Specify the fully qualified domain name (FQDN) of the SQL Server that will host the database instance that you are defining.</span></span>

<span data-ttu-id="448fe-106">Укажите экземпляр SQL Server, который будет принимать данные.</span><span class="sxs-lookup"><span data-stu-id="448fe-106">Specify the instance of SQL Server that will host the data.</span></span> <span data-ttu-id="448fe-107">Можно указать экземпляр по умолчанию или именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="448fe-107">You can specify the default instance, or you can specify a named instance.</span></span>

<span data-ttu-id="448fe-108">Следует четко представлять себе совмещение баз данных в определенных экземплярах.</span><span class="sxs-lookup"><span data-stu-id="448fe-108">Collocation of databases in specific instances should be very clearly understood.</span></span> <span data-ttu-id="448fe-109">Сведения о совмещении серверов и совмещении экземпляров баз данных см. в разделах [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) и [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment).</span><span class="sxs-lookup"><span data-stu-id="448fe-109">For details about server collocation and database instance collocation, see [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) and [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment).</span></span>