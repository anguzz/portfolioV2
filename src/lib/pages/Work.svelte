<script lang="ts">
  import Card from "$lib/components/Card.svelte";
  import Page from "$lib/components/Page.svelte";
  import { neutralBackground } from "$lib/utils/constants";

  type Job = {
    employer: string;
    title: string;
    startDate: Date;
    endDate: Date;
    description?: string;
    tasks: string[];
    tags?: string[];
  };
  const months = [
    "January",
    "February",
    "March",
    "April",
    "May",
    "June",
    "July",
    "August",
    "September",
    "October",
    "November",
    "December",
  ];
  const currentDate = new Date();
  function dateToString(date: Date) {
    return `${months[date.getMonth()]} ${date.getFullYear()}`;
  }
  function formatDateString(start: Date, end: Date) {
    return `${dateToString(start)} - ${dateToString(end) ?? "Present"}`;
  }
  const jobs: Array<Job> = [
    {
      employer: "Niagara Bottling",
      title: "Information Technology",
      startDate: new Date(2023, 4),
      endDate: currentDate,
      
      tasks: [
        "Develop customized Python/PowerShell scripts, streamlining internal Niagara application processes and reducing manual tasks",
        "Perform system audits, assessing user group permissions and their impact on security measures",
        "Conduct proactive threat analysis/response using Endpoint Detection and Response (EDR) to identify and neutralize potential threats",
        "Provision and configure user accounts & IoT devices for company resources and internal systems including AD, WMS, Oracle, Cisco, Duo MFA",
        "Utilize Microsoft Deployment Toolkit to automate the deployment of hardware",
      ],
      tags: [
        "Python","Powershell","Active Directory","Cybersecurity","IT"
      ],
    },
    {
      employer: "Ingram Micro",
      title: "Oracle Database Intern",
      startDate: new Date(2022, 5),
      endDate: new Date(2022, 8),
      
      tasks: [
        "Used ssh to connect to Linux servers and manually create/script oracle 19c prototype database applications",
        "Configured databases for backup and recovery using oracle's built in proprietary RMAN(recovery manager) to protect against data loss",
        "Monitor database performance, implement changes and apply new patches and versions when required",        
      ],
      tags: [
        "Oracle",
        "Databases",
        "Linux"
      ],
    },
    {
      employer: "Association for Computing Machinery, CSU-Fullerton",
      title: "Development Officer",
      startDate: new Date(2022, 3),
      endDate: currentDate,
      tasks: [
        "Delivered weekly educational workshops to students on various topics such in web development, such as leveraging APIs and understanding HTTP",
        "Oversaw semester-long projects and offered technical advice to aid team members in completing their personal projects ",
       
      ],
      tags: ["Github", "Web Development",],
    },
  ];

  export let backgroundClass = neutralBackground;
</script>

<Page id="work" title="Experience" {backgroundClass}>
  <div
    class="container mx-auto grid max-w-screen-xl gap-4 md:grid-cols-1 xl:grid-cols-2 3xl:grid-cols-4"
  >
    {#each jobs as job}
      <Card
        title={job.employer}
        subtitle={`${job.title}, ${formatDateString(
          job.startDate,
          job.endDate
        )}`}
        tags={job.tags}
      >
        {#if job.description}
          <div class="mb-1">
            {job.description ?? ""}
          </div>
        {/if}
        <ul class="list-disc list-inside">
          {#each job.tasks as task}
            <li>{task}</li>
          {/each}
        </ul>
      </Card>
    {/each}
  </div>
</Page>


