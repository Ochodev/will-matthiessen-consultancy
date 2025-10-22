# GoHighLevel CRM Setup & Implementation Guide

**A Comprehensive Guide by Will Matthiessen**  
*Specialized for Fitness Businesses & Health Entrepreneurs*

---

## Table of Contents

1. [Introduction](#introduction)
2. [Pre-Implementation Planning](#pre-implementation-planning)
3. [Account Setup & Configuration](#account-setup--configuration)
4. [Pipeline Architecture for Fitness Businesses](#pipeline-architecture-for-fitness-businesses)
5. [Automation Workflows](#automation-workflows)
6. [Lead Capture & Forms](#lead-capture--forms)
7. [Calendar & Booking System](#calendar--booking-system)
8. [SMS & Email Campaign Setup](#sms--email-campaign-setup)
9. [Membership Management](#membership-management)
10. [Integration Strategy](#integration-strategy)
11. [Training & Team Onboarding](#training--team-onboarding)
12. [Optimization & Scaling](#optimization--scaling)

---

## Introduction

GoHighLevel (GHL) is an all-in-one CRM and marketing platform that has become the industry standard for fitness businesses looking to streamline operations, automate member acquisition, and scale systematically. This guide reflects proven implementation strategies from working with dozens of fitness studios, personal training businesses, and health coaching practices.

### Why GoHighLevel for Fitness Businesses?

- **All-in-One Solution**: Replaces 5-10 different tools
- **Automation-First**: Reduces admin work by 70%+
- **Mobile-Optimized**: Manage your business from anywhere
- **White-Label Capable**: Brand it as your own
- **Cost-Effective**: One platform instead of multiple subscriptions

---

## Pre-Implementation Planning

### 1. Business Assessment

Before touching GoHighLevel, document your current state:

**Current Tools Audit:**
- Lead capture methods (Facebook, Instagram, website)
- Email marketing platform
- Booking/scheduling system
- Payment processor
- Membership management
- Communication channels (SMS, email, phone)

**Process Mapping:**
- How does someone become a lead?
- What's your follow-up sequence?
- How do trial members convert to paid?
- What's your onboarding process?
- How do you handle cancellations/objections?

**Success Metrics:**
- Current lead-to-trial conversion rate
- Trial-to-member conversion rate
- Average response time to new leads
- Monthly member churn rate
- Average lifetime value

### 2. Migration Strategy

**Phase 1: Foundation (Week 1-2)**
- Account setup
- Team member access
- Pipeline configuration
- Contact import

**Phase 2: Automation (Week 3-4)**
- Lead capture forms
- Automated follow-up sequences
- Booking system setup
- Initial workflows

**Phase 3: Integration (Week 5-6)**
- Website integration
- Social media connections
- Payment gateway setup
- Third-party tool connections

**Phase 4: Optimization (Ongoing)**
- A/B testing
- Workflow refinement
- Team training
- Performance monitoring

---

## Account Setup & Configuration

### Initial Account Configuration

1. **Agency/Location Setup**
   ```
   Settings → Account Settings → Business Information
   - Business name
   - Address (important for local SEO)
   - Phone number (will be your SMS sender)
   - Time zone (critical for automation timing)
   - Logo and branding
   ```

2. **Team Member Setup**
   ```
   Settings → Team → Add User
   
   Recommended Roles for Fitness Business:
   - Owner/Admin: Full access
   - Sales Manager: Pipeline + calendar + contacts
   - Front Desk Staff: Calendar + basic contact access
   - Coaches/Trainers: Calendar only
   ```

3. **Custom Fields Configuration**

   Create these custom fields under Settings → Custom Fields:
   
   **Contact Fields:**
   - `fitness_goal` (dropdown: Weight Loss, Muscle Gain, Athletic Performance, General Health)
   - `experience_level` (dropdown: Beginner, Intermediate, Advanced)
   - `injury_history` (text area)
   - `preferred_contact_method` (dropdown: Text, Email, Phone)
   - `member_status` (dropdown: Lead, Trial, Active, Paused, Cancelled)
   - `membership_type` (dropdown: Monthly, Annual, Drop-in)
   - `start_date` (date)
   - `trial_date` (date)
   - `referral_source` (text)
   - `monthly_value` (currency)

### Branding & White-Labeling

```
Settings → Domains
- Add custom domain for client-facing pages
- Set up email sending domain (improves deliverability)
- Configure SSL certificate
```

**Recommended Setup:**
- Forms: forms.yourbusiness.com
- Calendars: book.yourbusiness.com
- Email sender: hello@yourbusiness.com

---

## Pipeline Architecture for Fitness Businesses

### The Fitness Business Pipeline

A properly structured pipeline is the backbone of your CRM. Here's the proven structure:

```
Stage 1: NEW LEAD
↓
Stage 2: CONTACTED
↓
Stage 3: TRIAL BOOKED
↓
Stage 4: TRIAL COMPLETED
↓
Stage 5: PROPOSAL SENT
↓
Stage 6: MEMBER
↓
Stage 7: LOST/NURTURE
```

### Pipeline Configuration Steps

1. **Create Your Pipeline**
   ```
   Opportunities → Settings (gear icon) → Add Pipeline
   Name: "Member Acquisition Pipeline"
   ```

2. **Add Stages with Automation**

   **Stage 1: NEW LEAD**
   - Purpose: Every lead starts here
   - Auto-trigger: Welcome text + email
   - SLA: Contact within 5 minutes
   
   **Stage 2: CONTACTED**
   - Purpose: Initial contact made
   - Auto-trigger: Follow-up sequence if no response
   - Task: Log conversation notes
   
   **Stage 3: TRIAL BOOKED**
   - Purpose: Trial session scheduled
   - Auto-trigger: Booking confirmation + reminder sequence
   - Task: Send trial prep information
   
   **Stage 4: TRIAL COMPLETED**
   - Purpose: Attended trial session
   - Auto-trigger: Feedback request + membership offer
   - Task: Coach notes/assessment
   
   **Stage 5: PROPOSAL SENT**
   - Purpose: Membership options presented
   - Auto-trigger: Follow-up sequence (1 hour, 1 day, 3 days)
   - Task: Address objections
   
   **Stage 6: MEMBER**
   - Purpose: Active paying member
   - Auto-trigger: Welcome sequence + onboarding
   - Task: Schedule fitness assessment
   
   **Stage 7: LOST/NURTURE**
   - Purpose: Not ready now, stay in touch
   - Auto-trigger: Long-term nurture sequence
   - Task: Tag with loss reason

3. **Pipeline Automation Rules**
   ```
   Opportunities → Pipeline → Stage Settings → Automation
   
   For each stage:
   - When opportunity enters: Trigger workflow
   - When opportunity exits: Update tags
   - When opportunity stalls (48+ hours): Create task for follow-up
   ```

---

## Automation Workflows

Workflows are where GoHighLevel shines for fitness businesses. Here are the essential automations:

### 1. New Lead Welcome Sequence

**Trigger:** New contact created OR Form submission

**Workflow:**
```
Immediate:
├─ Send SMS: "Hey [First Name]! Thanks for your interest in [Business Name]. 
│  We're excited to help you reach your fitness goals! When's the best time 
│  for a quick call? - [Your Name]"
│
├─ Send Email: Welcome email with intro video
│
└─ Create Opportunity: Stage "NEW LEAD"

Wait 5 minutes:
└─ If no response → Create Task: "Call new lead [First Name]"

Wait 2 hours:
└─ If no response → Send SMS: "Quick question - what's your biggest fitness 
   challenge right now?"

Wait 24 hours:
└─ If no response → Send Email: Success stories + trial offer

Wait 3 days:
└─ If no response → Send SMS: "Last chance for [Limited Offer]"
```

### 2. Trial Booking Confirmation

**Trigger:** Trial appointment booked

**Workflow:**
```
Immediate:
├─ Send SMS: "Your trial session is booked for [Date] at [Time]! 
│  Here's what to bring: [Items]. See you soon!"
│
├─ Send Email: Detailed prep info + location/parking
│
├─ Update Opportunity: Move to "TRIAL BOOKED"
│
└─ Add Tag: "trial-scheduled"

24 hours before:
└─ Send SMS: "Reminder: Your trial is tomorrow at [Time]. Reply YES to confirm!"

2 hours before:
└─ Send SMS: "See you in 2 hours! Address: [Address]. Call if you need anything: [Phone]"

1 hour after appointment:
└─ If showed up → Trigger "Post-Trial Follow-Up" workflow
└─ If no-show → Trigger "No-Show Recovery" workflow
```

### 3. Post-Trial Conversion Sequence

**Trigger:** Trial appointment marked "Complete"

**Workflow:**
```
Immediate:
├─ Update Opportunity: Move to "TRIAL COMPLETED"
│
└─ Wait for manual trigger from coach

Within 1 hour (coach triggers):
├─ Send SMS: "Great session today [First Name]! Here's your personalized plan: [Link]"
│
└─ Send Email: Detailed proposal with pricing options

Wait 3 hours:
└─ If no response → Send SMS: "Have any questions about the membership options?"

Wait 24 hours:
└─ If no response → Create Task: "Call [First Name] to discuss membership"

Wait 2 days:
└─ If no response → Send Email: Testimonial video + FAQ

Wait 4 days:
└─ If no response → Send SMS: "Hi [First Name], wanted to follow up on your 
   trial. Any concerns I can address?"

Wait 7 days:
└─ If no membership → Move to nurture sequence
```

### 4. Member Onboarding Sequence

**Trigger:** Opportunity moved to "MEMBER" stage

**Workflow:**
```
Immediate:
├─ Send SMS: "Welcome to the team [First Name]! 🎉 You're officially a member!"
│
├─ Send Email: Welcome packet with member portal access
│
├─ Add Tag: "active-member"
│
├─ Update Custom Field: member_status = "Active"
│
└─ Create Task: "Schedule fitness assessment"

Day 2:
└─ Send Email: How to use the app + class schedule

Day 7:
└─ Send SMS: "How's your first week going? Any questions?"

Day 14:
└─ Create Task: "14-day check-in call"

Day 30:
├─ Send Email: "Your First Month Milestone!" + progress tracking info
│
└─ Create Task: "30-day assessment"

Day 60:
└─ Send Email: Request review/testimonial
```

### 5. Re-engagement/Win-Back Campaign

**Trigger:** Member cancels or pauses

**Workflow:**
```
Immediate:
├─ Update Opportunity: Move to "LOST/NURTURE"
│
├─ Add Tag: "cancelled-member"
│
└─ Create Task: "Exit interview call"

Wait 7 days:
└─ Send Email: "We miss you!" + feedback survey

Wait 30 days:
└─ Send SMS: "Quick question: What would it take to get you back?"

Wait 60 days:
└─ Send Email: New programs/special offer

Wait 90 days:
└─ Send SMS: Re-engagement offer (50% off first month back)

Every 90 days:
└─ Continue nurture sequence with valuable content
```

### 6. Birthday/Anniversary Campaigns

**Trigger:** Date-based (custom field or appointment date)

**Workflow:**
```
On Birthday:
├─ Send SMS: "Happy Birthday [First Name]! 🎂 Enjoy a free smoothie on us today!"
│
└─ Create Task: "Give birthday gift card"

On Member Anniversary:
├─ Send Email: "It's been [X] months/years! Look how far you've come!"
│
└─ Send SMS: Thank you message + special offer for referral
```

---

## Lead Capture & Forms

### Form Strategy for Fitness Businesses

**Essential Forms to Create:**

1. **Trial Signup Form**
2. **Contact/Info Request Form**
3. **Nutrition Coaching Interest Form**
4. **Class Schedule Request Form**
5. **Personal Training Application**

### Creating a High-Converting Trial Form

```
Sites → Forms → New Form
Name: "Free Trial Session"
Type: Embedded Form
```

**Form Fields:**
```
1. First Name* (text)
2. Email* (email)
3. Phone* (phone) - with SMS opt-in checkbox
4. What's your main fitness goal?* (dropdown)
   - Lose weight
   - Build muscle
   - Improve athletic performance
   - General health & wellness
   
5. Experience level (radio buttons)
   - Never worked out before
   - Some gym experience
   - Regular gym-goer
   
6. How did you hear about us? (text)
7. Preferred trial date (calendar picker)
```

**Form Settings:**
```
Success Action: Redirect to thank you page
Automation: Trigger "New Lead Welcome" workflow
Opportunity: Create in "NEW LEAD" stage
Tags: Add "trial-interest", "web-lead"
Notifications: Email to owner
```

### Embedding Forms

**On Website:**
```html
<!-- Direct embed -->
<iframe src="https://forms.yourbusiness.com/trial" width="100%" height="800px"></iframe>

<!-- Popup trigger -->
<button onclick="window.open('https://forms.yourbusiness.com/trial', 'popup', 'width=600,height=800')">
  Book Free Trial
</button>
```

**On Social Media:**
- Use form link in Instagram bio
- Facebook lead ads → webhook to GHL
- TikTok link in bio

---

## Calendar & Booking System

### Calendar Setup for Fitness Business

1. **Create Service Calendars**

   ```
   Calendars → New Calendar
   
   Recommended Calendars:
   - Trial Sessions (30 min)
   - Strategy Calls (45 min)
   - Personal Training (60 min)
   - Fitness Assessments (45 min)
   - Nutrition Consultations (30 min)
   ```

2. **Calendar Configuration**

   **For Trial Sessions Calendar:**
   ```
   Settings:
   ├─ Duration: 30 minutes
   ├─ Buffer: 15 minutes before/after
   ├─ Availability: Mon-Fri 6am-8pm, Sat 8am-2pm
   ├─ Booking Window: 2 hours min, 30 days max
   ├─ Max bookings: 1 per day per contact
   ├─ Confirmation: Required
   └─ Location: [Your Address] or Video Call
   
   Questions to Ask:
   1. What's your main fitness goal?
   2. Any injuries we should know about?
   3. How did you hear about us?
   ```

3. **Automated Notifications**

   ```
   Calendar → [Calendar Name] → Notifications
   
   Booking Confirmed:
   ├─ SMS to Contact: Confirmation + details
   ├─ Email to Contact: Prep info + parking
   ├─ Email to Team: New trial booked notification
   └─ Calendar Invite: Add to Google/Outlook calendar
   
   24hr Reminder:
   └─ SMS: "Looking forward to seeing you tomorrow!"
   
   2hr Reminder:
   └─ SMS: "See you in 2 hours!"
   
   Booking Cancelled:
   ├─ SMS to Contact: Cancellation confirmation
   ├─ Email to Team: Cancellation notification
   └─ Trigger Workflow: Reschedule sequence
   ```

4. **Team Member Assignment**

   ```
   For larger teams:
   - Round-robin: Distributes bookings evenly
   - Priority order: Senior coaches first
   - Specific calendar per coach
   - Availability override per team member
   ```

### Calendar Integration Best Practices

- **Google Calendar Sync**: Prevents double-booking
- **Stripe/Payment**: Collect deposit for PT sessions
- **Zoom Integration**: Automatic video links for virtual consultations
- **Widget Embedding**: Put calendar on website homepage

---

## SMS & Email Campaign Setup

### SMS Best Practices for Fitness

**Compliance First:**
- Always get explicit SMS consent
- Include opt-out option in every message
- Keep messages under 160 characters when possible
- Use personal, conversational tone

**Effective SMS Templates:**

```
1. Speed-to-Lead (within 5 min):
"Hi [First Name]! Got your inquiry about [Studio Name]. 
When's good for a quick call? - [Your Name] 📞"

2. Appointment Reminder:
"Hey [First Name]! Trial tomorrow at [Time]. 
Wear comfy clothes & bring water. Can't wait to meet you! 🏋️"

3. Post-Trial Follow-Up:
"Great session today! Here's your personalized membership plan: 
[Link]. Questions? Just reply!"

4. Re-engagement:
"[First Name] - we miss seeing you! Special comeback offer: 
50% off your first month back. Interested? 💪"

5. Class Full Alert:
"The [Class Name] is filling up fast! Only 3 spots left. 
Want me to save you one? Reply YES!"
```

### Email Campaign Setup

1. **Create Email Templates**

   ```
   Marketing → Email Templates → New Template
   
   Essential Templates:
   - Welcome Email
   - Trial Confirmation
   - Membership Proposal
   - Weekly Newsletter
   - Success Story Feature
   - Renewal Reminder
   - Win-Back Campaign
   ```

2. **Welcome Email Example**

   ```
   Subject: Welcome to [Studio Name]! Here's what to expect...
   
   Hi [First Name],
   
   Thanks for joining the [Studio Name] family! We're pumped to 
   help you reach your fitness goals.
   
   Here's what happens next:
   
   ✅ Book Your Free Trial → [Calendar Link]
   ✅ Watch: What to Expect → [Video Link]
   ✅ Meet the Team → [Team Page]
   
   Have questions? Just reply to this email or text me at [Phone].
   
   See you soon!
   
   [Your Name]
   [Title]
   
   P.S. Follow us on Instagram @[handle] for daily tips & motivation!
   ```

3. **Campaign Segmentation**

   ```
   Marketing → Campaigns → New Campaign
   
   Audience Segments:
   - Trial Members (last 30 days)
   - Active Members (6+ months)
   - At-Risk Members (no check-in 14+ days)
   - Cancelled Members (last 90 days)
   - Long-term Nurture (trial, didn't convert)
   ```

### Broadcast vs Automated Messages

**Broadcasts (One-time sends):**
- Holiday hours announcement
- New class launch
- Special event invitation
- Price change notice

**Automated (Workflow-based):**
- Welcome sequences
- Trial confirmations
- Member onboarding
- Re-engagement campaigns

---

## Membership Management

### Setting Up Membership Types

Use Custom Fields and Tags to manage memberships:

```
Custom Fields:
- membership_type: Monthly, Annual, Drop-in, Personal Training Package
- membership_start_date: Date
- membership_value: Currency
- payment_status: Current, Past Due, Cancelled
- billing_cycle_day: Number (1-31)
```

### Payment Integration

**Stripe Integration:**
```
Settings → Integrations → Stripe
- Connect Stripe account
- Set up recurring payment plans
- Configure payment links
- Enable automatic receipt emails
```

**Membership Products to Create:**
```
1. Monthly Unlimited: $199/month
2. 2x Per Week: $129/month
3. Annual Unlimited: $1999/year (save $400!)
4. 10-Session Package: $300
5. Personal Training: $80/session or $320/month (4 pack)
```

### Membership Workflows

**Payment Failed Workflow:**
```
Trigger: Stripe payment failed webhook

Actions:
├─ Update Custom Field: payment_status = "Past Due"
├─ Send SMS: "Hi [First Name], your payment didn't go through. 
│  Can you update your card? [Payment Link]"
├─ Wait 24 hours
├─ Send Email: Payment failed notice + how to update
├─ Wait 3 days
└─ Create Task: "Call [First Name] about failed payment"
```

**Renewal Reminder Workflow:**
```
Trigger: 7 days before membership_start_date anniversary

Actions:
├─ Send Email: "Your membership renews in 7 days. Thanks for being awesome!"
├─ Wait until renewal date
└─ Send SMS: "Welcome to another year/month! 🎉"
```

---

## Integration Strategy

### Essential Integrations for Fitness Businesses

1. **Stripe/PayPal** - Payment processing
2. **Google Calendar** - Prevent double-booking
3. **Facebook Lead Ads** - Auto-import leads
4. **Zapier/Make** - Connect other tools
5. **Zoom** - Virtual consultations
6. **Mindbody/ClassPass** - (if applicable)

### Facebook Lead Ads Integration

```
Settings → Integrations → Facebook
- Connect Facebook Ads account
- Map form fields to GHL custom fields
- Set automation trigger for new leads
- Test with sample lead
```

**Mapping Example:**
```
Facebook Field → GHL Field
email → email
full_name → first_name (parse) + last_name (parse)
phone_number → phone
fitness_goal → custom field: fitness_goal
```

### Zapier Advanced Integrations

**Example Zaps:**

1. **Mindbody → GoHighLevel**
   - Trigger: New Mindbody client
   - Action: Create contact in GHL
   - Action: Add tag "mindbody-member"

2. **GoHighLevel → Google Sheets**
   - Trigger: New opportunity in "MEMBER" stage
   - Action: Add row to tracking sheet
   - Benefit: Real-time revenue dashboard

3. **Typeform → GoHighLevel**
   - Trigger: New Typeform submission
   - Action: Create contact + start workflow
   - Benefit: Better survey experience

---

## Training & Team Onboarding

### Staff Training Checklist

**Front Desk Staff:**
- [ ] How to add new contacts manually
- [ ] How to book appointments
- [ ] How to send quick SMS/email
- [ ] How to update opportunity stages
- [ ] How to log notes
- [ ] Emergency contact protocols

**Sales/Coaches:**
- [ ] Understanding the pipeline stages
- [ ] How to manage opportunities
- [ ] How to use email/SMS templates
- [ ] How to schedule follow-ups
- [ ] Reporting and metrics
- [ ] Mobile app usage

**Owners/Managers:**
- [ ] Dashboard analytics
- [ ] Workflow management
- [ ] Creating broadcasts
- [ ] Team performance reports
- [ ] Integration management
- [ ] Troubleshooting common issues

### Creating Standard Operating Procedures (SOPs)

**Document these processes in GHL:**

1. **New Lead Response Protocol**
   ```
   1. Lead comes in (form, phone, walk-in)
   2. Create contact in GHL (if not auto-created)
   3. Send welcome text within 5 minutes
   4. Create opportunity in NEW LEAD stage
   5. Attempt phone call within 15 minutes
   6. Log call notes in contact
   7. Move to CONTACTED stage
   8. Book trial or add to follow-up sequence
   ```

2. **Trial Day Checklist**
   ```
   Before Trial:
   - Confirm appointment in GHL calendar
   - Review contact notes/goals
   - Prepare assessment forms
   
   During Trial:
   - Take notes on fitness level, goals, objections
   - Get photos/measurements (with permission)
   - Present membership options
   
   After Trial:
   - Log session notes in GHL immediately
   - Move opportunity to TRIAL COMPLETED
   - Send membership proposal within 1 hour
   - Set follow-up task for next day
   ```

---

## Optimization & Scaling

### Key Metrics to Track

**Pipeline Metrics:**
```
Reporting → Pipeline → Dashboard

Track:
- Lead-to-Trial conversion rate (target: 40%+)
- Trial-to-Member conversion rate (target: 50%+)
- Average time in each stage
- Pipeline velocity
- Stage-specific drop-off points
```

**Communication Metrics:**
```
Reporting → Conversations

Track:
- Average response time (target: <5 minutes)
- Open rates (email target: 25%+, SMS: 95%+)
- Click-through rates
- Conversation-to-appointment rate
```

**ROI Metrics:**
```
Track in custom fields + export to sheets:
- Cost per lead by source
- Customer acquisition cost
- Lifetime value by membership type
- Monthly recurring revenue
- Churn rate
```

### A/B Testing Framework

**What to Test:**

1. **SMS Response Times**
   - Test: Immediate vs 5-min delay on welcome text
   - Measure: Response rate, trial booking rate

2. **Trial Offer Timing**
   - Test: Offer in first text vs third contact
   - Measure: Trial booking rate

3. **Email Subject Lines**
   - Test: Question vs statement vs emoji
   - Measure: Open rate, click rate

4. **Follow-Up Frequency**
   - Test: 5 touches in 7 days vs 3 touches in 14 days
   - Measure: Response rate, annoyance rate (opt-outs)

### Scaling Strategies

**When you're ready to grow:**

1. **Multi-Location Setup**
   ```
   Settings → Add Location
   - Separate pipelines per location
   - Location-specific automations
   - Centralized reporting
   - Franchise-ready structure
   ```

2. **White-Label for Gyms (Agency Model)**
   ```
   - Create sub-accounts for each gym client
   - Clone your successful workflows
   - Custom branding per client
   - Recurring revenue from GHL resale
   ```

3. **Advanced Automation**
   ```
   - AI chatbot for website
   - SMS appointment confirmations with Google Maps link
   - Automated class waitlist management
   - Predictive churn analysis
   - Automated review requests
   ```

4. **Advanced Reporting**
   ```
   - Daily automated reports to email
   - TV dashboard in gym showing real-time metrics
   - Weekly team performance leaderboard
   - Monthly business review automation
   ```

---

## Troubleshooting Common Issues

### Issue: Low Email Deliverability

**Solution:**
- Set up custom sending domain
- Authenticate with SPF/DKIM records
- Warm up email gradually (don't blast 1000 emails day 1)
- Clean your contact list (remove inactive contacts)
- Avoid spam trigger words

### Issue: SMS Not Delivering

**Solution:**
- Verify phone number format (country code included)
- Check contact SMS opt-in status
- Ensure A2P 10DLC registration complete (US)
- Monitor for carrier blocks
- Keep messages conversational (not spammy)

### Issue: Workflows Not Triggering

**Solution:**
- Check workflow is published (not draft)
- Verify trigger conditions match exactly
- Check contact doesn't already exist in workflow
- Review workflow logs for errors
- Test with fresh test contact

### Issue: Calendar Double-Bookings

**Solution:**
- Connect Google Calendar 2-way sync
- Set appropriate buffer times
- Enable "check conflicts" setting
- Set max bookings per day/week
- Train team on blocking personal time

---

## Quick Start Checklist

Use this checklist for your first 30 days:

### Week 1: Foundation
- [ ] Complete account setup and branding
- [ ] Add team members with appropriate access
- [ ] Create custom fields for fitness business
- [ ] Build member acquisition pipeline
- [ ] Import existing contacts (with SMS consent)

### Week 2: Automation
- [ ] Create trial booking form
- [ ] Set up trial booking calendar
- [ ] Build "New Lead Welcome" workflow
- [ ] Build "Trial Confirmation" workflow
- [ ] Create basic email templates

### Week 3: Implementation
- [ ] Embed forms on website
- [ ] Connect Facebook Lead Ads
- [ ] Set up Stripe payment integration
- [ ] Create membership products/pricing
- [ ] Build "Post-Trial Follow-Up" workflow

### Week 4: Optimization
- [ ] Train team on GHL basics
- [ ] Document SOPs
- [ ] Set up reporting dashboard
- [ ] Launch first email campaign
- [ ] Monitor and adjust workflows based on data

---

## Conclusion

GoHighLevel is a powerful tool, but it's only as effective as your implementation strategy. The key is to:

1. **Start Simple**: Don't try to automate everything day one
2. **Focus on Impact**: Prioritize the workflows that save the most time
3. **Test & Iterate**: Use data to improve your processes
4. **Train Your Team**: Technology only works if people use it
5. **Stay Consistent**: Review and optimize monthly

This guide reflects real-world implementation experience with fitness businesses. Adapt these strategies to your specific business model, and you'll create a systematic, scalable member acquisition machine.

---

## Need Help?

This guide is part of Will Matthiessen's consultancy practice. For personalized implementation support:

- **1-on-1 GoHighLevel Setup**: Custom implementation for your fitness business
- **Team Training Sessions**: Get your staff up to speed quickly
- **Workflow Optimization**: Audit and improve your existing setup
- **Ongoing Support**: Monthly optimization calls

Visit [Your Website] or email [Your Email] to learn more.

---

**Document Version:** 1.0  
**Last Updated:** 2025  
**Author:** Will Matthiessen  
**Specialization:** CRM Systems for Fitness & Health Businesses