---
title: Установка группами Майкрософт, с помощью MSI (с SCCM)
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/31/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Администраторы могут использовать команды MSI-файла (с SCCM) чтобы dpeloy группами Майкрософт для выбора пользователей или компьютеров в пакетном режиме.
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7db13d34eec5f04a1d73a85bbd4bed4044f3cfc7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012683"
---
<a name="install-microsoft-teams-using-msi-with-sccm"></a><span data-ttu-id="6a813-103">Установка группами Майкрософт, с помощью MSI (с SCCM)</span><span class="sxs-lookup"><span data-stu-id="6a813-103">Install Microsoft Teams using MSI (with SCCM)</span></span>
===========================================

<span data-ttu-id="6a813-104">Корпорация Майкрософт условии, что файл MSI для "Администраторы" для массового развертывания групп для выбора пользователей или компьютеров.</span><span class="sxs-lookup"><span data-stu-id="6a813-104">Microsoft has provided an MSI file for admins to bulk deploy Teams to select users or machines.</span></span> <span data-ttu-id="6a813-105">Администраторы могут использовать этот файл, чтобы удаленно развертывание групп, чтобы пользователи не имеют для ручной загрузки приложения группы.</span><span class="sxs-lookup"><span data-stu-id="6a813-105">Admins can use this file to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="6a813-106">System Center Configuration Manager (SCCM) — это основное средство, используемое с помощью MSI-файлов для управляемых развертываний.</span><span class="sxs-lookup"><span data-stu-id="6a813-106">System Center Configuration Manager (SCCM) is the primary tool used with MSI files for managed deployments.</span></span>

                                                                               
