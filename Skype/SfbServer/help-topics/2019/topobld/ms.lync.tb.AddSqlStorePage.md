---
title: Добавление хранилища SQL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы определить новый SQL Store, то есть указать базу данных на основе SQL Server и экземпляр SQL Server (экземпляр по умолчанию или именовый экземпляр), необходимо указать следующее.
ms.openlocfilehash: 46cdbed683abc2121ce4038b6692f1f73f8abc0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824509"
---
# <a name="add-sql-store"></a><span data-ttu-id="9a7c6-103">Добавление хранилища SQL</span><span class="sxs-lookup"><span data-stu-id="9a7c6-103">Add SQL Store</span></span>

<span data-ttu-id="9a7c6-104">Чтобы определить новый SQL Store, то есть указать базу данных на основе SQL Server и экземпляр SQL Server (экземпляр по умолчанию или именовый экземпляр), необходимо указать следующее.</span><span class="sxs-lookup"><span data-stu-id="9a7c6-104">To define a new SQL Store, which means that you are specifying a SQL Server-based database and an instance of SQL Server—either a default instance or a named instance—you specify the following.</span></span>

<span data-ttu-id="9a7c6-105">Укажите полное доменное имя (FQDN) SQL Server, в которой будет работать определяющий экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="9a7c6-105">Specify the fully qualified domain name (FQDN) of the SQL Server that will host the database instance that you are defining.</span></span>

<span data-ttu-id="9a7c6-106">Укажите экземпляр SQL Server, в который будут велись данные.</span><span class="sxs-lookup"><span data-stu-id="9a7c6-106">Specify the instance of SQL Server that will host the data.</span></span> <span data-ttu-id="9a7c6-107">Можно указать экземпляр по умолчанию или именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="9a7c6-107">You can specify the default instance, or you can specify a named instance.</span></span>

<span data-ttu-id="9a7c6-108">Следует четко представлять себе совмещение баз данных в определенных экземплярах.</span><span class="sxs-lookup"><span data-stu-id="9a7c6-108">Collocation of databases in specific instances should be very clearly understood.</span></span> <span data-ttu-id="9a7c6-109">Сведения о совмещении серверов и совмещении экземпляров баз данных см. в разделах [Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx) и [Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx).</span><span class="sxs-lookup"><span data-stu-id="9a7c6-109">For details about server collocation and database instance collocation, see [Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx) and [Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx).</span></span>


