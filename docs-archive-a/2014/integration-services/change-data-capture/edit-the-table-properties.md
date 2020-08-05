---
title: Editar as propriedades da tabela | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- editTabProps
ms.assetid: 95ea72ba-8e40-4177-a963-0fb4d10c56e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1ba0809b99474704ec0e93e417a04d776bb26d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571522"
---
# <a name="edit-the-table-properties"></a><span data-ttu-id="a0112-102">Editar as propriedades da tabela</span><span class="sxs-lookup"><span data-stu-id="a0112-102">Edit the Table Properties</span></span>
  <span data-ttu-id="a0112-103">Use esta caixa de diálogo para editar as colunas específicas da tabela selecionada onde as alterações estão sendo capturadas.</span><span class="sxs-lookup"><span data-stu-id="a0112-103">Use this dialog box to edit the specific columns from the selected table where changes are being captured.</span></span> <span data-ttu-id="a0112-104">Você também pode editar as informações de **Função de Segurança** e **Instância de Captura** .</span><span class="sxs-lookup"><span data-stu-id="a0112-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
### <a name="to-edit-the-columns-to-include-in-the-cdc-instance"></a><span data-ttu-id="a0112-105">Para editar as colunas a serem incluídas na instância CDC</span><span class="sxs-lookup"><span data-stu-id="a0112-105">To edit the columns to include in the CDC instance</span></span>  
  
1.  <span data-ttu-id="a0112-106">Siga um ou ambos destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="a0112-106">Do one or both of the following:</span></span>  
  
    -   <span data-ttu-id="a0112-107">Marque a caixa de seleção ao lado de qualquer coluna adicional que você quer incluir.</span><span class="sxs-lookup"><span data-stu-id="a0112-107">Select the check box next to any additional column you want to include.</span></span>  
  
    -   <span data-ttu-id="a0112-108">Desmarque a caixa de seleção ao lado de qualquer coluna que você não quer mais incluir.</span><span class="sxs-lookup"><span data-stu-id="a0112-108">Clear the check box next to any column that you no longer want to include.</span></span>  
  
### <a name="to-edit-the-security-role"></a><span data-ttu-id="a0112-109">Para editar a função de segurança</span><span class="sxs-lookup"><span data-stu-id="a0112-109">To edit the Security Role</span></span>  
  
1.  <span data-ttu-id="a0112-110">Digite um novo nome ou edite o nome da função de segurança no campo **Função de Segurança** .</span><span class="sxs-lookup"><span data-stu-id="a0112-110">Type a new name or edit the name of the security role in the **Security Role** field.</span></span>  
  
### <a name="to-create-a-new-capture-instance"></a><span data-ttu-id="a0112-111">Para criar uma nova instância de captura</span><span class="sxs-lookup"><span data-stu-id="a0112-111">To create a new capture instance</span></span>  
  
1.  <span data-ttu-id="a0112-112">Na seção **Função de Segurança** , no campo **Nome** , insira um nome para a instância de captura.</span><span class="sxs-lookup"><span data-stu-id="a0112-112">In the **Security Role** section, **Name** field enter a name for the capture instance.</span></span> <span data-ttu-id="a0112-113">Por padrão, o nome inserido no campo é o nome da instância de captura atual com **_NEW** no final do nome (por exemplo, **instância_antiga_NEW**).</span><span class="sxs-lookup"><span data-stu-id="a0112-113">By default, the name entered in the field is the name of the current capture instance with **_NEW** added to the end of the name (for example, **old_instance_NEW**).</span></span>  
  
2.  <span data-ttu-id="a0112-114">Salve a instância de captura como um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a0112-114">Save the capture instance as one of the following:</span></span>  
  
    -   <span data-ttu-id="a0112-115">**Nova Instância de Captura**: neste caso, uma nova instância de captura é salva e a instância de captura antiga não é excluída.</span><span class="sxs-lookup"><span data-stu-id="a0112-115">**New Capture Instance**: In this case a new capture instance is saved and the old capture instance is not deleted.</span></span>  
  
         <span data-ttu-id="a0112-116">**Observação**: você não pode ter mais que duas instâncias de captura por tabela.</span><span class="sxs-lookup"><span data-stu-id="a0112-116">**Note**: You can have no more than two capture instances per table.</span></span> <span data-ttu-id="a0112-117">Se já houver duas instâncias de captura, esta opção não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="a0112-117">If there are already two capture instances, this option is not available.</span></span>  
  
    -   <span data-ttu-id="a0112-118">**Substituir Existente**: neste caso, a instância de captura atual é excluída e é substituída pela instância de captura criada.</span><span class="sxs-lookup"><span data-stu-id="a0112-118">**Replace Existing**: In this case the current capture instance is deleted and replaced by the capture instance you created.</span></span> <span data-ttu-id="a0112-119">Se houver duas instâncias de captura definidas para esta tabela, você deverá selecionar uma para substituir.</span><span class="sxs-lookup"><span data-stu-id="a0112-119">If there are two capture instances defined for this table, you must select one to replace.</span></span>  
  
 <span data-ttu-id="a0112-120">**Observação**: você pode remover uma instância de captura da lista de tabelas na guia **Tabela** .</span><span class="sxs-lookup"><span data-stu-id="a0112-120">**Note**: You can remove a capture instance from the list of tables in the **Table** tab.</span></span>  
  
 <span data-ttu-id="a0112-121">Depois de terminar de inserir as informações nesta caixa de diálogo, clique em **OK** para aceitar as alterações.</span><span class="sxs-lookup"><span data-stu-id="a0112-121">After you finish entering the information in this dialog box, click **OK** to accept the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0112-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a0112-122">See Also</span></span>  
 <span data-ttu-id="a0112-123">[Como editar as propriedades de instância CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="a0112-123">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="a0112-124">Fazer alterações nas tabelas selecionadas para capturar alterações</span><span class="sxs-lookup"><span data-stu-id="a0112-124">Make Changes to the Tables Selected for Capturing Changes</span></span>](make-changes-to-the-tables-selected-for-capturing-changes.md)  
  
  
