## Hi there, I hope you to find my profile useful and interesting👋
```c
#include <stdio.h>
#include <stdlib.h> // for strtol()
#include <pthread.h>
#include <stdatomic.h>

static _Atomic int thread_count;

void *hello(void *rank);


int main(int argc, char *argv[])
{
    long thread; // Use of long in case of 64 bits system
    pthread_t *thread_handles;

    if(argc < 2)
    {
        fprintf(stderr, "Usage: %s <number of threads> \n", argv[0]);

        return 1; //Indicate an error
    }

    // Get the number of threads
    thread_count = strtol(argv[1], NULL, 10);

    if(thread_count <= 0 || thread_count > 12)
    {
        fprintf(stderr, "Error: Number of threads(%d) is outside system limits. \nPlease provide a value in a range between 2 and 12.", thread_count);

        return 1; // Return error
    }

    thread_handles = malloc(thread_count*sizeof(pthread_t));

    for(thread = 0; thread < thread_count; thread++)
    {
        pthread_create(&thread_handles[thread], NULL, hello, (void *) thread);
    }

    for(thread = 0; thread < thread_count; thread++)
    {
        pthread_join(thread_handles[thread], NULL);
    }

    free(thread_handles);

    puts("Exiting execution...");


    return 0;

}


void *hello(void *rank)
{
    long my_rank = (long) rank;

    printf("Welcome to my github account from rank %ld of %d.\n", my_rank, thread_count);


    return NULL;
}
```


I am a Computer Scientist with 3+ years of experience in high-performance computing (HPC), AI, and system validation.
Specialized in CPU and accelerator workloads with strong skills in performance tuning, application optimization, and
system-level validation. Experienced in using SIMD, multithreading, MPI, and OpenMP to enhance scalability, efficiency,
and runtime performance, primarily in C and C++. Experienced in:

1. Performance profiling and benchmarking using a wide variety of tools.
2. Selecting parallel-friendly algorithms and data structures for compute kernels.
3. Estimating and improving application speed-up and efficiency on multicore and heterogeneous systems.
   
Passionate about AI, deep learning. MCS thesis involved developing a deep convolutional neural network for mammography
density classification, in collaboration with the Universidad Autónoma de Guadalajara (UAG), Centro Médico
Nacional de Occidente (CMNO), and the Jalisco State Government. Also explored NLP, fine-tuning LLMs, and deployed
GPU-accelerated models on small cloud clusters as side projects.

##  🌱 I’m currently learning ...

- How to boost memory capacity using different types of compression.
- How to provide visibility into memory usage across HPC systems.

##  🔭 I’m looking to collaborate on ...

- Processor, accelerator, memory, storage, interconnect, and system architectures, including architectures based on future and emerging hardware for HPC systems.
- Programming languages, paradigms, and execution models, including domain-specific languages and scientific problem-solving software environments for HPC and parallel computing
- Compilers, runtime systems and system software, including optimization and support for hardware resources and energy management.
- High-performance algorithms and applications including machine learning and large-scale data analytics, as well as the implementation and deployment of algorithms and applications on large-   scale systems.
- Tools for measurement, modeling, compression, analysis, and visualization of performance, energy, or other quantitative properties of high-performance computing systems.

##  ⚡ Fun facts about me

Fun Fact 1: 
I love to read about anything, I consider myself a really curious person, who thinks some of the most wonderfult capacities of being human is the ability to learn and get impressed with all the knowledge that exists in this world. "We are all ignorant, but we are not all ignorant of the same things."

Fun Fact 2:
I really love cats, I love them in all their colors, and races.

