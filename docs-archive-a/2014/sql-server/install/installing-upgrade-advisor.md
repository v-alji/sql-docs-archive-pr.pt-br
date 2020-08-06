---
title: Instalando o supervisor de atualização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: 1b7d6eca-1df1-47df-bbba-0fc485706a95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 40f214b01f3e2066708a060c5f3ad1e8aa4a0a23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679639"
---
# <a name="installing-upgrade-advisor"></a><span data-ttu-id="5472b-102">Instalando o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="5472b-102">Installing Upgrade Advisor</span></span>
  <span data-ttu-id="5472b-103">O local da instalação do Supervisor de Atualização do SQL Server 2014 depende do que você analisará.</span><span class="sxs-lookup"><span data-stu-id="5472b-103">Where you install SQL Server 2014 Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="5472b-104">O Supervisor de Atualização oferece suporte para análise remota de todos os componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , com exceção do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5472b-104">Upgrade Advisor supports remote analysis of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="5472b-105">Se não estiver verificando instâncias do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], você pode instalar o Supervisor de Atualização em qualquer computador que pode se conectar a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], e que esteja em conformidade com [Upgrade Advisor Prerequisites](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="5472b-105">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the [Upgrade Advisor Prerequisites](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span></span> <span data-ttu-id="5472b-106">Se você estiver verificando instâncias do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], será necessário instalar o Supervisor de Atualização no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="5472b-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="5472b-107">Execute o arquivo **SQLUA.msi** para instalar o Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="5472b-107">Run the **SQLUA.msi** file to install Upgrade Advisor.</span></span> <span data-ttu-id="5472b-108">Você pode instalar do prompt de comando para instalações autônomas e automatizadas.</span><span class="sxs-lookup"><span data-stu-id="5472b-108">You can install from the command prompt for unattended and automated installations.</span></span> <span data-ttu-id="5472b-109">Consulte [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) para obter a sintaxe e exemplos.</span><span class="sxs-lookup"><span data-stu-id="5472b-109">See [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) for syntax and examples.</span></span>  
  
 <span data-ttu-id="5472b-110">Obter SQLUA.msi:</span><span class="sxs-lookup"><span data-stu-id="5472b-110">Get SQLUA.msi:</span></span>  
  
-   <span data-ttu-id="5472b-111">Na pasta **redist** da mídia do produto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5472b-111">In the **redist** folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product media.</span></span>  
  
-   <span data-ttu-id="5472b-112">Como parte do [download do SQL 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=42295).</span><span class="sxs-lookup"><span data-stu-id="5472b-112">As part of the [SQL 2014 Feature Pack download](https://www.microsoft.com/download/details.aspx?id=42295).</span></span>  
  
## <a name="uninstalling-upgrade-advisor"></a><span data-ttu-id="5472b-113">Desinstalando o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="5472b-113">Uninstalling Upgrade Advisor</span></span>  
 <span data-ttu-id="5472b-114">Você pode desinstalar o Supervisor de Atualização usando **Adicionar ou Remover Programas**.</span><span class="sxs-lookup"><span data-stu-id="5472b-114">You can uninstall Upgrade Advisor by using **Add or Remove Programs**.</span></span> <span data-ttu-id="5472b-115">A sintaxe do prompt de comando também dá suporte à remoção/desinstalação.</span><span class="sxs-lookup"><span data-stu-id="5472b-115">The command prompt syntax also supports removal/uninstall.</span></span>  
  
  
