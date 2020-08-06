---
title: Importar as políticas para uma única instância | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: bc5bcd87-663f-41d9-bb7b-b3e083cd63df
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0464bc6f4dcd6326a4b8f222cb4b3128f21561ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684956"
---
# <a name="import-the-policies-to-a-single-instance"></a><span data-ttu-id="a1ed5-102">Importar as políticas para uma única instância</span><span class="sxs-lookup"><span data-stu-id="a1ed5-102">Import the Policies to a Single Instance</span></span>
  <span data-ttu-id="a1ed5-103">Nesta tarefa, você importará as políticas de práticas recomendadas que deseja agendar no Gerenciamento Baseado em Políticas em uma única instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1ed5-103">In this task, you will import the best practices policies that you want to schedule into Policy-Based Management on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a1ed5-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a1ed5-104">Prerequisites</span></span>  
 <span data-ttu-id="a1ed5-105">Você deve executar este procedimento em um servidor que está executando o [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="a1ed5-105">You must perform this procedure on a server that is running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span>  
  
### <a name="import-the-best-practices-policies-for-the-database-engine"></a><span data-ttu-id="a1ed5-106">Importar as políticas de práticas recomendadas para o Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="a1ed5-106">Import the best practices policies for the Database Engine</span></span>  
  
1.  <span data-ttu-id="a1ed5-107">Inicie o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]e conecte-se ao [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1ed5-107">Start [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a1ed5-108">No Pesquisador de Objetos, expanda **Gerenciamento**e, em seguida, expanda **Gerenciamento de Políticas**.</span><span class="sxs-lookup"><span data-stu-id="a1ed5-108">In Object Explorer, expand **Management**, and then expand **Policy Management**.</span></span>  
  
3.  <span data-ttu-id="a1ed5-109">Clique com o botão direito do mouse em **Políticas**e clique em **Importar Política**.</span><span class="sxs-lookup"><span data-stu-id="a1ed5-109">Right-click **Policies**, and then click **Import Policy**.</span></span>  
  
4.  <span data-ttu-id="a1ed5-110">Na caixa de diálogo **importar** , ao lado da caixa **arquivos a serem importados** , clique no botão de reticências (**...**).</span><span class="sxs-lookup"><span data-stu-id="a1ed5-110">In the **Import** dialog box, next to the **Files to import** box, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="a1ed5-111">Na lista **Examinar** , navegue até a pasta a seguir, que contém as políticas de práticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="a1ed5-111">In the **Look in** list, browse to the following folder, which contains the best practices policies:</span></span>  
  
     <span data-ttu-id="a1ed5-112">**C:\Arquivos de Programas (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="a1ed5-112">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a1ed5-113">O caminho do arquivo pode variar, dependendo de onde você instalou os arquivos de programa do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , do sistema operacional em execução (32 bits ou 64 bits) e do identificador de idioma.</span><span class="sxs-lookup"><span data-stu-id="a1ed5-113">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
6.  <span data-ttu-id="a1ed5-114">Na caixa de diálogo **Selecionar Política** , selecione um ou mais arquivos de política.</span><span class="sxs-lookup"><span data-stu-id="a1ed5-114">In the **Select Policy** dialog box, select one or more policy files.</span></span>  
  
     <span data-ttu-id="a1ed5-115">Para selecionar arquivos não adjacentes, clique em um arquivo, mantenha a tecla CTRL pressionada e clique em cada arquivo adicional.</span><span class="sxs-lookup"><span data-stu-id="a1ed5-115">To select nonadjacent files, click one file, hold down the CTRL key, and then click each additional file.</span></span> <span data-ttu-id="a1ed5-116">Para selecionar arquivos adjacentes, clique no primeiro arquivo da sequência, mantenha a tecla SHIFT pressionada e clique no último arquivo.</span><span class="sxs-lookup"><span data-stu-id="a1ed5-116">To select adjacent files, click the first file in the sequence, hold down the SHIFT key, and then click the last file.</span></span>  
  
7.  <span data-ttu-id="a1ed5-117">Após terminar de selecionar os arquivos, clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a1ed5-117">When you are finished selecting files, click **Open**.</span></span>  
  
8.  <span data-ttu-id="a1ed5-118">Na caixa de diálogo **Importar** , verifique se a lista **Estado da política** está definida como **Preservar o estado da política ao importar** (o padrão) e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1ed5-118">In the **Import** dialog box, make sure that the **Policy state** list is set to **Preserve policy state on import** (the default), and then click **OK**.</span></span>  
  
     <span data-ttu-id="a1ed5-119">As políticas são importadas no nó **Políticas** em **Gerenciamento de Políticas**.</span><span class="sxs-lookup"><span data-stu-id="a1ed5-119">The policies are imported into the **Policies** node under **Policy Management**.</span></span> <span data-ttu-id="a1ed5-120">Por padrão, as políticas importadas são definidas como modo de avaliação "Sob demanda."</span><span class="sxs-lookup"><span data-stu-id="a1ed5-120">By default, the imported policies are set to "On demand" evaluation mode.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a1ed5-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a1ed5-121">Next Steps</span></span>  
 [<span data-ttu-id="a1ed5-122">Agendar as políticas</span><span class="sxs-lookup"><span data-stu-id="a1ed5-122">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
  
