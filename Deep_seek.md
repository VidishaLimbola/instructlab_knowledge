# DeepSeek

## History

In February 2016, High-Flyer was co-founded by AI enthusiast Liang Wenfeng, who had been trading since the 2007–2008 financial crisis while attending Zhejiang University. The company began stock-trading using a GPU-dependent deep learning model on October 21, 2016. Prior to this, they used CPU-based models, mainly linear models. Most trading was driven by AI by the end of 2017.
In 2019, Liang established High-Flyer as a hedge fund focused on developing and using AI trading algorithms. By 2021, High-Flyer exclusively used AI in trading, often using Nvidia chips.
Initial computing cluster Fire-Flyer began construction in 2019 and finished in 2020, at a cost of 200 million yuan. It contained 1,100 GPUs interconnected at a rate of 200 Gbps. It was 'retired' after 1.5 years in operation. 
In 2021, Liang began stockpiling Nvidia GPUs for an AI project. According to 36Kr, Liang acquired 10,000 Nvidia A100 GPUs before the United States restricted chip sales to China. Computing cluster Fire-Flyer 2 began construction in 2021 with a budget of 1 billion yuan. 
It was reported that in 2022, Fire-Flyer 2's capacity had been utilized at over 96%, totaling 56.74 million GPU hours. 27% was used to support scientific computing outside the company. 
During 2022, Fire-Flyer 2 had 5000 PCIe A100 GPUs in 625 nodes, each containing 8 GPUs. At the time, they exclusively used PCIe instead of DGX version of A100, since at the time the models they trained could fit within a single 40 GB GPU VRAM, so there was no need for the higher bandwidth of DGX (i.e. they required only data parallelism but not model parallelism). Later, they incorporated NVLinks and NCCL, to train larger models that required model parallelism.
On 14 April 2023, High-Flyer announced the start of an artificial general intelligence lab dedicated to research developing AI tools separate from High-Flyer's financial business. Incorporated on 17 July 2023, with High-Flyer as the investor and backer, the lab became its own company, DeepSeek. Venture capital firms were reluctant to provide funding, as they considered it unlikely that the venture would be able to quickly generate an "exit".
On 16 May 2023, the company Beijing DeepSeek Artificial Intelligence Basic Technology Research Co., Ltd. incorporated under the control of Hangzhou DeepSeek Artificial Intelligence Basic Technology Research Co., Ltd. As of May 2024, Liang owned 84% of DeepSeek through two shell corporations.
On 2 November 2023, DeepSeek released its first model, DeepSeek Coder. On 29 November 2023, DeepSeek released the DeepSeek – LLM series of models.: section 5 
On 9 January 2024, they released 2 DeepSeek – MoE models (Base and Chat).
In April 2024, they released 3 DeepSeek – Math models: Base, Instruct, and RL.
DeepSeek-V2 was released in May 2024. It offered performance for a low price, and became the catalyst for China's AI model price war. It was dubbed the "Pinduoduo of AI", and other Chinese tech giants such as ByteDance, Tencent, Baidu, and Alibaba cut the price of their AI models. Despite its low price, it was profitable compared to its money-losing rivals .
In June 2024, the DeepSeek - Coder V2 series was released.
DeepSeek V2.5 was released in September and updated in December 2024.
On 20 November 2024, DeepSeek-R1-Lite-Preview became accessible via API and chat.
In December 2024, they released a base model DeepSeek - V3-Base and a chat model DeepSeek-V3. 
On 20 January 2025, DeepSeek released its first free chatbot app, based on the DeepSeek-R1 model, for iOS and Android; by 27 January, DeepSeek had surpassed ChatGPT as the most-downloaded free app on the iOS App Store in the United States, causing Nvidia's share price to drop by 18%.

## Strategy

DeepSeek is focused on research and has not detailed plans for commercialization. This allows its technology to avoid the most stringent provisions of China's AI regulations, such as requiring consumer-facing technology to comply with government controls on information.
DeepSeek's hiring preferences target technical abilities rather than work experience; most new hires are either recent university graduates or developers whose AI careers are less established. Likewise, the company recruits individuals without any computer science background to help its technology understand more knowledge areas, such as poetry and China's notoriously difficult college admissions exams (Gaokao).

## Training framework

High-Flyer/DeepSeek operates at least two computing clusters, Fire-Flyer (萤火一号) and Fire-Flyer 2 (萤火二号). Fire-Flyer 2 consists of co-designed software and hardware architecture. On the hardware side, Nvidia GPUs use 200 Gbps interconnects. The cluster is divided into two "zones", and the platform supports cross-zone tasks. The network topology was two fat trees, chosen for high bisection bandwidth. On the software side are:

3FS (Fire-Flyer File System): A distributed parallel file system, specifically designed for asynchronous random reads. It uses Direct I/O and RDMA Read. In contrast to standard Buffered I/O, Direct I/O does not cache data. Caching is useless for this case, since each data read is random, and is not reused.
hfreduce: Library for asynchronous communication, originally designed to replace Nvidia Collective Communication Library (NCCL). It is mainly used for allreduce, especially of gradients during backpropagation. It is asynchronously run on the CPU to avoid blocking kernels on the GPU. It uses two-tree broadcast like NCCL.
hfai.nn: Software library of commonly used operators for neural network training, similar to torch.nn in PyTorch.
HaiScale Distributed Data Parallel (DDP): Parallel training library that implements various forms of parallelism such as Data Parallelism (DP), Pipeline Parallelism (PP), Tensor Parallelism (TP), Experts Parallelism (EP), Fully Sharded Data Parallel (FSDP) and Zero Redundancy Optimizer (ZeRO). It is similar to PyTorch DDP, which uses NCCL on the backend.
HAI Platform: Various applications such as task scheduling, fault handling, and disaster recovery.
As of 2022, Fire-Flyer 2 had 5000 PCIe A100 GPUs in 625 nodes, each containing 8 GPUs. . They later incorporated NVLinks and NCCL, to train larger models that required model parallelism.

## Release history



## Modules



## Banning

In February 2025 the Australian goverment ordered its public servants to delete DeepSeek, this was after a cyber security firm warned of it's output and the data it collects.The United States Navy followed suit and instructed all its members not to use DeepSeek, ordinary citizen could also face jail time or be fined under the newly proposed law if found using the app.

## See also

Artificial intelligence industry in China

## Notes



## References



## External links


Official website 
DeepSeek on GitHub
DeepSeek on Hugging Face
Official API documentation
Anthology of DeepSeek papers
Research blog of High-Flyer

