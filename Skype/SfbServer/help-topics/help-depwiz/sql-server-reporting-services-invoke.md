---
title: Службы SQL Server Reporting Services (вызов)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: После предоставления необходимой информации для развертывания сервера мониторинга отчетов Microsoft SQL Server 2008 R2 или для служб Microsoft SQL Server 2012 отчета, на странице выполнение команд отображается сводка по переданные команды для установки отчеты служб отчетов SQL Server.
ms.openlocfilehash: f1cc4ee2f2a53ea8e6d3ba1f1fcd24c59c915990
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873642"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="15354-103">Службы SQL Server Reporting Services (вызов)</span><span class="sxs-lookup"><span data-stu-id="15354-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="15354-104">После предоставления необходимой информации для развертывания сервера мониторинга отчетов Microsoft SQL Server 2008 R2 или для служб Microsoft SQL Server 2012 отчета, на странице выполнение команд отображается сводка по переданные команды для установки отчеты служб отчетов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="15354-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="15354-p101">Просмотрите сводку команд и обратите внимание на все сообщения об ошибках и предупреждающие сообщения, отображаемые для команд. Если сформирован файл журнала, для просмотра этого файла выберите его в раскрывающемся списке в окне сводки и нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="15354-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="15354-107">Для отчетов служб Reporting Services, для успешного развертывания и получить доступ к отчетам, после завершения развертывания, необходимо иметь TCP/IP в брандмауэре Windows откройте порт 80 (и при необходимости TCP-порт 443 для протокола SSL, если назначить сертификат для служб отчетов) Повышенной безопасности на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="15354-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="15354-108">Дополнительные сведения см [Настройка брандмауэра Windows на разрешение доступа к SQL Server](https://go.microsoft.com/fwlink/p/?linkId=218031) для Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="15354-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="15354-109">После просмотра сводки нажмите кнопку **Готово** , чтобы завершить установку отчетов в SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="15354-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

