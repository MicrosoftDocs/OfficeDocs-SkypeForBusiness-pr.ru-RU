---
title: Службы SQL Server Reporting Services (вызов)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: После предоставления необходимых данных для развертывания отчетов сервера мониторинга в Microsoft SQL Server 2008 R2 или службах отчетов Microsoft SQL Server 2012, команды выполнения страницы выводят сводку команд, которые выдаются для установки отчеты служб SQL Server Reporting Services.
ms.openlocfilehash: 758e8cb14511a2b190a9401c9064c3e57a87a4fd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700734"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="af304-103">Службы SQL Server Reporting Services (вызов)</span><span class="sxs-lookup"><span data-stu-id="af304-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="af304-104">После предоставления необходимых данных для развертывания отчетов сервера мониторинга в Microsoft SQL Server 2008 R2 или службах отчетов Microsoft SQL Server 2012, команды выполнения страницы выводят сводку команд, которые выдаются для установки отчеты служб SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="af304-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="af304-p101">Просмотрите сводку команд и обратите внимание на все сообщения об ошибках и предупреждающие сообщения, отображаемые для команд. Если сформирован файл журнала, для просмотра этого файла выберите его в раскрывающемся списке в окне сводки и нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="af304-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="af304-107">Для успешной развертки отчетов служб Reporting Services и получения доступа к отчетам после развертывания необходимо иметь порт TCP/IP 80 (и, при необходимости, TCP-порт 443 для SSL, если вы назначаете сертификат для служб Reporting Services) в брандмауэре Windows в режиме повышенной безопасности на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="af304-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="af304-108">Дополнительные сведения можно найти в разделе [Настройка брандмауэра Windows для обеспечения доступа к SQL Server](https://go.microsoft.com/fwlink/p/?linkId=218031) для Microsoft sql Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="af304-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="af304-109">После просмотра реферата нажмите кнопку **Готово** , чтобы завершить установку отчетов в службах SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="af304-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

