---
title: 'Tarefa 10: Configurando o domínio composto para usar o serviço de dados de referência | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 752eefde-8b87-4f54-878e-9963ccbadc8e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d70966b4cde110540bf5008eda4e3151fe32f28d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685999"
---
# <a name="task-10-configuring-composite-domain-to-use-reference-data-service"></a><span data-ttu-id="5bfd9-102">Tarefa 10: Configurando o domínio composto para usar o serviço de dados de referência</span><span class="sxs-lookup"><span data-stu-id="5bfd9-102">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>
  <span data-ttu-id="5bfd9-103">Nesta tarefa, você configura o domínio composto de **validação de endereço** para usar o serviço de verificação de **endereço de dados Melissa** .</span><span class="sxs-lookup"><span data-stu-id="5bfd9-103">In this task, you configure the **Address Validation** composite domain to use the **Melissa Data - Address Check** service.</span></span> <span data-ttu-id="5bfd9-104">Em runtime, durante a atividade de limpeza, o DQS passa os valores de domínios existentes no domínio Address Validation para o serviço de limpeza.</span><span class="sxs-lookup"><span data-stu-id="5bfd9-104">At runtime, during cleansing activity, DQS passes the values of domains in the Address Validation domain to the service for cleansing.</span></span> <span data-ttu-id="5bfd9-105">Consulte [mapear domínio/domínio de composição para dados de referência](https://msdn.microsoft.com/library/hh213030.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5bfd9-105">See [Map Domain/Composite Domain to Reference Data](https://msdn.microsoft.com/library/hh213030.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="5bfd9-106">Na página principal do **cliente do DQS**, clique em **fornecedores (gerenciamento de domínio)** em **bases de dados de conhecimento recentes** para iniciar a página de **Gerenciamento de domínio** .</span><span class="sxs-lookup"><span data-stu-id="5bfd9-106">In the main page of **DQS Client**, click **Suppliers (Domain Management)** under **Recent Knowledge Bases** to launch the **Domain Management** page.</span></span>  
  
2.  <span data-ttu-id="5bfd9-107">Selecione o domínio composto **validação de endereço** na **lista de domínios**.</span><span class="sxs-lookup"><span data-stu-id="5bfd9-107">Select the **Address Validation** composite domain in the **list of domains**.</span></span>  
  
3.  <span data-ttu-id="5bfd9-108">No painel direito, alterne para a guia **dados de referência** .</span><span class="sxs-lookup"><span data-stu-id="5bfd9-108">In the right pane, switch to the **Reference Data** tab.</span></span>  
  
     <span data-ttu-id="5bfd9-109">![Guia Dados de Referência](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Guia Dados de Referência")</span><span class="sxs-lookup"><span data-stu-id="5bfd9-109">![Reference Data Tab](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Reference Data Tab")</span></span>  
  
4.  <span data-ttu-id="5bfd9-110">Clique no botão **procurar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="5bfd9-110">Click **Browse** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="5bfd9-111">Na caixa de diálogo **Catálogo de provedores de dados de referência online** , marque a **caixa de seleção** ao lado de **Melissa verificação de endereço de dados**.</span><span class="sxs-lookup"><span data-stu-id="5bfd9-111">On the **Online Reference Data Providers Catalog** dialog box, select **check box** next to **Melissa Data - Address Check**.</span></span>  
  
     <span data-ttu-id="5bfd9-112">![Selecionar Melissa Data - Verificação de Endereço](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Selecionar Melissa Data - Verificação de Endereço")</span><span class="sxs-lookup"><span data-stu-id="5bfd9-112">![Select Melissa Data - Address Check](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Select Melissa Data - Address Check")</span></span>  
  
6.  <span data-ttu-id="5bfd9-113">No painel direito, na seção **esquema** , mapeie o domínio da **linha de endereço** para o item de esquema da linha de **Endereço (M)** usando a lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5bfd9-113">In the right pane, in the **Schema** section, map **Address Line** domain to the **Address Line (M)** schema item by using the drop-down list.</span></span>  
  
     <span data-ttu-id="5bfd9-114">![Mapear Item de Esquema do RDS para Domínio](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Mapear Item de Esquema do RDS para Domínio")</span><span class="sxs-lookup"><span data-stu-id="5bfd9-114">![Map RDS Schema Item to Domain](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Map RDS Schema Item to Domain")</span></span>  
  
7.  <span data-ttu-id="5bfd9-115">Clique no botão **Adicionar entrada de esquema (+)** na barra de ferramentas para criar uma entrada na lista.</span><span class="sxs-lookup"><span data-stu-id="5bfd9-115">Click **Add Schema Entry (+)** button on the toolbar to create an entry in the list.</span></span>  
  
     <span data-ttu-id="5bfd9-116">![Botão de barra de ferramentas Adicionar Entrada de Esquema](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Botão de barra de ferramentas Adicionar Entrada de Esquema")</span><span class="sxs-lookup"><span data-stu-id="5bfd9-116">![Add Schema Entry Toolbar Button](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Add Schema Entry Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="5bfd9-117">Mapeie os seguintes domínios do DQS usando as listas suspensas como mostra a imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="5bfd9-117">Map the following DQS domains by using the drop-down lists as shown in the following picture.</span></span>  
  
     <span data-ttu-id="5bfd9-118">![Mapear Itens de Esquema do RDS para Domínios](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Mapear Itens de Esquema do RDS para Domínios")</span><span class="sxs-lookup"><span data-stu-id="5bfd9-118">![Map RDS Schema Items to Domains](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Map RDS Schema Items to Domains")</span></span>  
  
9. <span data-ttu-id="5bfd9-119">Clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5bfd9-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="5bfd9-120">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5bfd9-120">Next Step</span></span>  
 [<span data-ttu-id="5bfd9-121">Tarefa 11: Publicando a base de dados de conhecimento</span><span class="sxs-lookup"><span data-stu-id="5bfd9-121">Task 11: Publishing the Knowledge Base</span></span>](../../2014/tutorials/task-11-publishing-the-knowledge-base.md)  
  
  
