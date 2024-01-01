# Fine-Tune-LLM
In this project, we have focused on certain aspects like how we can Tune a state-of-the-art Large language Model like Deci-7B and other fundamental aspects in Fine-tuning 
Open Source LLM's.

## These are the key points that are covered in this project:-

 1. How to curate Data that has to be ingested for fine-tuning open-source LLM. In our case DECI-7B
 2. We will understand what is diff. bw Multi Head attention vs Muti Query Attention vs Grouped Query Attention
 3. How to use Gradio to make a complete chatbot using fine-tuned LLM (DECI-7B) with a complete example.

## Q- Why we are focusing on Grouped query attention?

 Ans. - Deci-7B uses GQA along with LORA to reach the top of open source LLM's leaderboard.

# What is diff MQA vs MHA vs GQA?

MHA - Multi-Head Attention - As stated in this type of attention mechanism, we have As Many heads as we have no query vectors. 
Example - If we have 8 query vectors we will have 8 key vectors whose product will later on be multiplied with 8 value vectors and we will get our attention span.

MQA - Multi query Attention - In this type of attention we have only 1 head and 1 key vector for N query vectors (in our case 8 query vectors). The benefit of this flavor of attention is It has much less memory footprint and is much faster because we don't have to manage multiple heads and key vectors.

GQA - Grouped query attention - So this flavor of attention is a combination of MHA and MQA. It is made with the intention to cut down on the losses registered when implementing MQA. In this version, we will make groups of query vectors and then for the M groups we have made for N query vectors, we will have M keys and M Heads. 
Example - Supposedly we have made groups of 2 then for 8 query vectors we will have 4 groups it means we have 4 keys and 4 heads which is much efficient than MHA and on benchmarks registers less losses on MQA.
