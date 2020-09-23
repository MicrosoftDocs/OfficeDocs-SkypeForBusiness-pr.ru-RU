---
title: Добавление хранилища SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Чтобы определить новое хранилище SQL, это означает, что вы указываете базу данных на основе SQL Server и экземпляр SQL Server — либо экземпляр по умолчанию, либо именованный экземпляр — вы задаете следующее.
ms.openlocfilehash: 261cc9ca3b0f792c9ab6566ba24f1d4d7236937a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217130"
---
# <a name="add-sql-store"></a><span data-ttu-id="e5f4a-103">Добавление хранилища SQL</span><span class="sxs-lookup"><span data-stu-id="e5f4a-103">Add SQL Store</span></span>

<span data-ttu-id="e5f4a-104">Чтобы определить новое хранилище SQL, это означает, что вы указываете базу данных на основе SQL Server и экземпляр SQL Server — либо экземпляр по умолчанию, либо именованный экземпляр — вы задаете следующее.</span><span class="sxs-lookup"><span data-stu-id="e5f4a-104">To define a new SQL Store, which means that you are specifying a SQL Server-based database and an instance of SQL Server—either a default instance or a named instance—you specify the following.</span></span>

<span data-ttu-id="e5f4a-105">Укажите полное доменное имя (FQDN) сервера SQL Server, на котором будет размещаться определяемый экземпляр базы данных.</span><span class="sxs-lookup"><span data-stu-id="e5f4a-105">Specify the fully qualified domain name (FQDN) of the SQL Server that will host the database instance that you are defining.</span></span>

<span data-ttu-id="e5f4a-106">Укажите экземпляр SQL Server, на котором будут размещаться данные.</span><span class="sxs-lookup"><span data-stu-id="e5f4a-106">Specify the instance of SQL Server that will host the data.</span></span> <span data-ttu-id="e5f4a-107">Можно указать экземпляр по умолчанию или именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e5f4a-107">You can specify the default instance, or you can specify a named instance.</span></span>

<span data-ttu-id="e5f4a-108">Следует четко представлять себе совмещение баз данных в определенных экземплярах.</span><span class="sxs-lookup"><span data-stu-id="e5f4a-108">Collocation of databases in specific instances should be very clearly understood.</span></span> <span data-ttu-id="e5f4a-109">Сведения о совмещении серверов и совмещении экземпляров баз данных см. в разделах [Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx) и [Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx).</span><span class="sxs-lookup"><span data-stu-id="e5f4a-109">For details about server collocation and database instance collocation, see [Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx) and [Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx).</span></span>


