---
title: Criar scripts usando modelos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ed48014c-3fc9-48ff-8c0f-8d1822195f14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b404ecc505e93c302e4c737f9c0b0161d9015519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681320"
---
# <a name="create-scripts-using-templates"></a><span data-ttu-id="28e4d-102">Criar scripts usando modelos</span><span class="sxs-lookup"><span data-stu-id="28e4d-102">Create Scripts Using Templates</span></span>
  <span data-ttu-id="28e4d-103">O Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] fornece um grande número de modelos de script que contêm as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] para muitas tarefas comuns.</span><span class="sxs-lookup"><span data-stu-id="28e4d-103">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides a large number of script templates containing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for many common tasks.</span></span> <span data-ttu-id="28e4d-104">Esses modelos contêm parâmetros para obter os valores fornecidos pelo usuário, como um nome de tabela.</span><span class="sxs-lookup"><span data-stu-id="28e4d-104">These templates contain parameters for the user-provided values such as a table name.</span></span> <span data-ttu-id="28e4d-105">Usando os parâmetros, você pode digitar o nome uma vez e depois copiar automaticamente o nome em todos os locais necessários dentro do script.</span><span class="sxs-lookup"><span data-stu-id="28e4d-105">Using the parameters, you can type the name once and then automatically copy the name to all the necessary locations within the script.</span></span> <span data-ttu-id="28e4d-106">Você pode escrever seus próprios modelos personalizados para oferecer suporte aos scripts escritos com frequência.</span><span class="sxs-lookup"><span data-stu-id="28e4d-106">You can write your own custom templates to support the scripts that you write most often.</span></span> <span data-ttu-id="28e4d-107">Também é possível reorganizar a árvore de modelo, movendo modelos ou criando pastas novas para armazenar os modelos.</span><span class="sxs-lookup"><span data-stu-id="28e4d-107">You can also reorganize the template tree, moving templates or creating new folders to hold the templates.</span></span> <span data-ttu-id="28e4d-108">No procedimento a seguir, você usará um modelo para criar um banco de dados, especificando o modelo de ordenação.</span><span class="sxs-lookup"><span data-stu-id="28e4d-108">In the following practice, you will use a template to create a database, specifying collation template.</span></span>  
  
## <a name="using-templates"></a><span data-ttu-id="28e4d-109">Usando modelos</span><span class="sxs-lookup"><span data-stu-id="28e4d-109">Using Templates</span></span>  
  
#### <a name="to-create-a-script-using-a-template"></a><span data-ttu-id="28e4d-110">Para criar um script usando um modelo</span><span class="sxs-lookup"><span data-stu-id="28e4d-110">To create a script using a template</span></span>  
  
1.  <span data-ttu-id="28e4d-111">No [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], no menu **Exibir** , clique em **Gerenciador de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="28e4d-111">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="28e4d-112">Os modelos do Explorador de Modelos são organizados em grupos.</span><span class="sxs-lookup"><span data-stu-id="28e4d-112">The templates in Template Explorer are organized into groups.</span></span> <span data-ttu-id="28e4d-113">Expanda **Banco de Dados**e clique duas vezes em **Criar Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="28e4d-113">Expand **Database**, and then double-click **Create Database**.</span></span>  
  
3.  <span data-ttu-id="28e4d-114">Na caixa de diálogo **Conectar ao Mecanismo de Banco de Dados** , complete as informações de conexão e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="28e4d-114">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="28e4d-115">Uma nova janela do Editor de Consultas será aberta, exibindo o conteúdo do modelo **Criar Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="28e4d-115">A new Query Editor window opens, containing the contents of the **Create Database** template.</span></span>  
  
4.  <span data-ttu-id="28e4d-116">No menu **Consulta** , clique em **Especificar Valores para Parâmetros de Modelo**.</span><span class="sxs-lookup"><span data-stu-id="28e4d-116">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="28e4d-117">Na caixa de diálogo **Especificar Valores para Parâmetros de Modelo** , a coluna **Valor** contém um valor sugerido para o parâmetro **Database_Name** .</span><span class="sxs-lookup"><span data-stu-id="28e4d-117">In the **Specify Values for Template Parameters** dialog box, the **Value** column contains a suggested value for the **Database_Name** parameter.</span></span> <span data-ttu-id="28e4d-118">No caixa de parâmetro **Nome do Banco de Dados** , digite **Marketing**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="28e4d-118">In the **Database Name** parameter box, type **Marketing**, and then click **OK**.</span></span> <span data-ttu-id="28e4d-119">Observe que "Marketing" é inserido no script em vários locais.</span><span class="sxs-lookup"><span data-stu-id="28e4d-119">Note how "Marketing" is inserted into the script in several locations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="28e4d-120">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="28e4d-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="28e4d-121">Criar modelos personalizados</span><span class="sxs-lookup"><span data-stu-id="28e4d-121">Create Custom Templates</span></span>](lesson-3-2-create-custom-templates.md)  
  
  
