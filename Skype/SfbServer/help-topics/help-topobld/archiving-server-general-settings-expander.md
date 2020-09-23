---
title: Расширитель общих настроек сервера архивации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 'В построителе топологий можно изменить свойства отдельного сервера, на котором выполняется архивация, щелкнув правой кнопкой мыши сервер, на котором выполняется архивация, в дереве консоли и нажав кнопку действие на панели инструментов или щелкнув задачу в области действия, а затем выбрав команду Изменить свойства и изменив любые из следующих параметров:'
ms.openlocfilehash: d160b9e7294719ff2251e95e5cc2ab72dd3a6ffd
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216900"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="ba6ed-103">Расширитель общих настроек сервера архивации</span><span class="sxs-lookup"><span data-stu-id="ba6ed-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="ba6ed-104">В построителе топологий можно изменить свойства отдельного сервера, на котором выполняется архивация, щелкнув правой кнопкой мыши сервер, на котором выполняется архивация, в дереве консоли и нажав кнопку **действие** на панели инструментов или щелкнув задачу в области действия, а затем выбрав команду **изменить свойства** и изменив любые из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="ba6ed-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="ba6ed-105">**Полное доменное имя**. Служит для изменения полного доменного имени сервера, который следует использовать как сервер архивации.</span><span class="sxs-lookup"><span data-stu-id="ba6ed-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="ba6ed-p101">**Хранилище SQL**. Служит для изменения экземпляра SQL Server, который используется для базы данных архивации SQL Server. Если изменить базу данных SQL Server на сервере архивации, необходимо перезапустить сервер архивации, чтобы изменение вступило в силу.</span><span class="sxs-lookup"><span data-stu-id="ba6ed-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="ba6ed-p102">**Общая папка файлов.** Служит для изменения папки, которая используется для архивации хранилища файлов. Если изменить общую папку файлов сервера архивации, необходимо перезапустить сервер архивации, чтобы изменение вступило в силу. Кроме того, необходимо переместить файлы конференции в папку нового файлового хранилища во избежание утраты архивных файлов конференций.</span><span class="sxs-lookup"><span data-stu-id="ba6ed-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ba6ed-111">Чтобы изменить пулы, связанные с сервером архивации, выберите параметр **Изменение свойств** для отдельного узла интерфейсного пула или узла устройства для обеспечения связи в филиалах, сопоставленного в настоящее время с сервером архивации.</span><span class="sxs-lookup"><span data-stu-id="ba6ed-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba6ed-112">Узел архивации содержит сервер архивации, если этот сервер был раньше добавлен в топологию с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="ba6ed-112">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder.</span></span> <span data-ttu-id="ba6ed-113">В этом списке можно изменить свойства любого сервера архивации.</span><span class="sxs-lookup"><span data-stu-id="ba6ed-113">You can edit properties for any server running Archiving in the list.</span></span> <span data-ttu-id="ba6ed-114">Однако архивация мгновенных сообщений и веб-конференций (обмен сообщениями) невозможна, пока вы не настроите службу для сервера, на котором выполняется архивация.</span><span class="sxs-lookup"><span data-stu-id="ba6ed-114">However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

